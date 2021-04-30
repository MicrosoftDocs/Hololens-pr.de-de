---
title: Aktualisieren von HoloLens
description: Erfahren Sie, wie Sie Ihre HoloLens-Buildnummer überprüfen, über Geräteupdates auf dem Laufenden bleiben, am Insiders-Programm teilnehmen und Updates zurücksetzen.
keywords: Vorgehensweise, Aktualisieren, Rollback, HoloLens, Überprüfen des Builds, Buildnummer
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
ms.sourcegitcommit: ad53ba5edd567a18f0c172578d78db3190701650
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/19/2021
ms.locfileid: "108308809"
---
# <a name="update-hololens"></a><span data-ttu-id="e50e8-104">Aktualisieren von HoloLens</span><span class="sxs-lookup"><span data-stu-id="e50e8-104">Update HoloLens</span></span>

<span data-ttu-id="e50e8-105">HoloLens verwendet Windows Update wie andere Windows 10 Geräte.</span><span class="sxs-lookup"><span data-stu-id="e50e8-105">HoloLens uses Windows Update, just like other Windows 10 devices.</span></span> <span data-ttu-id="e50e8-106">Ihre HoloLens lädt Systemupdates automatisch herunter und installiert sie, sobald sie an den Strom angeschlossen und mit dem Internet verbunden ist, auch wenn sie sich im Standbymodus befindet.</span><span class="sxs-lookup"><span data-stu-id="e50e8-106">Your HoloLens will automatically download and install system updates whenever it is plugged-in to power and connected to the Internet, even when it is in standby.</span></span>

<span data-ttu-id="e50e8-107">In diesem Artikel werden HoloLens-Tools für:</span><span class="sxs-lookup"><span data-stu-id="e50e8-107">This article will walk through HoloLens tools for:</span></span>

- <span data-ttu-id="e50e8-108">Anzeigen der aktuellen Betriebssystemversion (Buildnummer)</span><span class="sxs-lookup"><span data-stu-id="e50e8-108">viewing your current operating system version (build number)</span></span>
- <span data-ttu-id="e50e8-109">Überprüfen auf Updates</span><span class="sxs-lookup"><span data-stu-id="e50e8-109">checking for updates</span></span>
- <span data-ttu-id="e50e8-110">Manuelles Aktualisieren von HoloLens</span><span class="sxs-lookup"><span data-stu-id="e50e8-110">manually updating HoloLens</span></span>
- <span data-ttu-id="e50e8-111">Rollback zu einem älteren Update</span><span class="sxs-lookup"><span data-stu-id="e50e8-111">rolling back to an older update</span></span>

## <a name="check-your-operating-system-version-build-number"></a><span data-ttu-id="e50e8-112">Überprüfen der Betriebssystemversion (Buildnummer)</span><span class="sxs-lookup"><span data-stu-id="e50e8-112">Check your operating system version (build number)</span></span>

<span data-ttu-id="e50e8-113">Sie können die Systemversionsnummer (Buildnummer) überprüfen, indem Sie die App Einstellungen öffnen und **System**  >  **about** auswählen.</span><span class="sxs-lookup"><span data-stu-id="e50e8-113">You can verify the system version number, (build number) by opening the Settings app and selecting **System** > **About**.</span></span>

## <a name="check-for-updates-and-manually-update"></a><span data-ttu-id="e50e8-114">Suchen nach Updates und manuelles Aktualisieren</span><span class="sxs-lookup"><span data-stu-id="e50e8-114">Check for updates and manually update</span></span>

<span data-ttu-id="e50e8-115">Sie können jederzeit in den Einstellungen nach Updates suchen.</span><span class="sxs-lookup"><span data-stu-id="e50e8-115">You can check for updates any time in settings.</span></span>  <span data-ttu-id="e50e8-116">So können Sie verfügbare Updates anzeigen und nach neuen Updates suchen:</span><span class="sxs-lookup"><span data-stu-id="e50e8-116">To see available updates and check for new updates:</span></span>

1. <span data-ttu-id="e50e8-117">Öffnen Sie die App **Einstellungen**.</span><span class="sxs-lookup"><span data-stu-id="e50e8-117">Open the **Settings** app.</span></span>
1. <span data-ttu-id="e50e8-118">Navigieren Sie zu **Update & Security**  >  **Windows Update**.</span><span class="sxs-lookup"><span data-stu-id="e50e8-118">Navigate to **Update & Security** > **Windows Update**.</span></span>
1. <span data-ttu-id="e50e8-119">Wählen Sie **Nach Updates suchen** aus.</span><span class="sxs-lookup"><span data-stu-id="e50e8-119">Select **Check for updates**.</span></span>

<span data-ttu-id="e50e8-120">Wenn ein Update verfügbar ist, beginnt es mit dem Herunterladen der neuen Version.</span><span class="sxs-lookup"><span data-stu-id="e50e8-120">If an update is available, it will start downloading the new version.</span></span> <span data-ttu-id="e50e8-121">Wählen Sie nach Abschluss des Downloads die Schaltfläche **Jetzt neu starten** aus, um die Installation auszulösen.</span><span class="sxs-lookup"><span data-stu-id="e50e8-121">After the download is complete, select the **Restart Now** button to trigger the installation.</span></span> <span data-ttu-id="e50e8-122">Wenn Ihr Gerät unter 40 % liegt und nicht angeschlossen ist, startet der Neustart nicht mit der Installation des Updates.</span><span class="sxs-lookup"><span data-stu-id="e50e8-122">If your device is below 40% and not plugged in, restarting will not start installing the update.</span></span>

<span data-ttu-id="e50e8-123">Während Ihre HoloLens das Update installiert, werden spinnende Zahnrad und eine Statusanzeige angezeigt.</span><span class="sxs-lookup"><span data-stu-id="e50e8-123">While your HoloLens is installing the update, it will display spinning gears and a progress indicator.</span></span> <span data-ttu-id="e50e8-124">Deaktivieren Sie Ihre HoloLens während dieser Zeit nicht.</span><span class="sxs-lookup"><span data-stu-id="e50e8-124">Do not turn off your HoloLens during this time.</span></span> <span data-ttu-id="e50e8-125">Er wird automatisch neu gestartet, sobald die Installation abgeschlossen ist.</span><span class="sxs-lookup"><span data-stu-id="e50e8-125">It will restart automatically once it has completed the installation.</span></span>

<span data-ttu-id="e50e8-126">HoloLens wendet ein Update nach dem anderen an.</span><span class="sxs-lookup"><span data-stu-id="e50e8-126">HoloLens applies one update at a time.</span></span>  <span data-ttu-id="e50e8-127">Wenn Ihre HoloLens mehr als eine Version hinter der neuesten version liegt, müssen Sie den Updateprozess möglicherweise mehrmals ausführen, um ihn vollständig auf dem neuesten Stand zu halten.</span><span class="sxs-lookup"><span data-stu-id="e50e8-127">If your HoloLens is more than one version behind the latest you may need to run through the update process multiple times to get it fully up to date.</span></span>

## <a name="go-back-to-a-previous-version---hololens-2"></a><span data-ttu-id="e50e8-128">Zurück zu einer früheren Version – HoloLens 2</span><span class="sxs-lookup"><span data-stu-id="e50e8-128">Go back to a previous version - HoloLens 2</span></span>

<span data-ttu-id="e50e8-129">In einigen Fällen sollten Sie zu einer früheren Version der HoloLens-Software zurückkommen.</span><span class="sxs-lookup"><span data-stu-id="e50e8-129">In some cases, you might want to go back to a previous version of the HoloLens software.</span></span> <span data-ttu-id="e50e8-130">Hierzu können Sie den Advanced Recovery Companion verwenden, um Ihre HoloLens auf die frühere Version zurückzusetzen.</span><span class="sxs-lookup"><span data-stu-id="e50e8-130">You can do this by using the Advanced Recovery Companion to reset your HoloLens to the earlier version.</span></span>

> [!NOTE]
> <span data-ttu-id="e50e8-131">Wenn Sie zu einer früheren Version zurückkommen, werden Ihre persönlichen Dateien und Einstellungen gelöscht.</span><span class="sxs-lookup"><span data-stu-id="e50e8-131">Going back to an earlier version deletes your personal files and settings.</span></span>

<span data-ttu-id="e50e8-132">Führen Sie die folgenden Schritte aus, um zu einer HoloLens 2 version of HoloLens 2 zu wechseln:</span><span class="sxs-lookup"><span data-stu-id="e50e8-132">To go back to a previous version of HoloLens 2, follow these steps:</span></span>

1. <span data-ttu-id="e50e8-133">Stellen Sie sicher, dass keine Smartphones oder Windows-Geräte an Ihren PC angeschlossen sind.</span><span class="sxs-lookup"><span data-stu-id="e50e8-133">Make sure that you don't have any phones or Windows devices plugged in to your PC.</span></span>
1. <span data-ttu-id="e50e8-134">Laden Sie auf Ihrem PC den [Advanced Recovery Companion aus](https://www.microsoft.com/p/advanced-recovery-companion/9p74z35sfrs8?activetab=pivot:overviewtab) dem Microsoft Store.</span><span class="sxs-lookup"><span data-stu-id="e50e8-134">On your PC, download the [Advanced Recovery Companion](https://www.microsoft.com/p/advanced-recovery-companion/9p74z35sfrs8?activetab=pivot:overviewtab) from the Microsoft Store.</span></span>
1. <span data-ttu-id="e50e8-135">Laden Sie [die neueste version HoloLens 2 herunter.](https://aka.ms/hololens2download)</span><span class="sxs-lookup"><span data-stu-id="e50e8-135">Download the [most recent HoloLens 2 release](https://aka.ms/hololens2download).</span></span>
1. <span data-ttu-id="e50e8-136">Wenn Sie diese Downloads abgeschlossen haben, öffnen Sie **Datei-Explorer**  >  **Downloads**.</span><span class="sxs-lookup"><span data-stu-id="e50e8-136">When you have finished these downloads, open **File explorer** > **Downloads**.</span></span> <span data-ttu-id="e50e8-137">Klicken Sie mit der rechten Maustaste auf den zip-Ordner, den Sie gerade heruntergeladen haben, und wählen Sie **Alle** extrahieren  >  **aus,** um ihn zu entzippen.</span><span class="sxs-lookup"><span data-stu-id="e50e8-137">Right-click the zipped folder that you just downloaded, and select **Extract all** > **Extract** to unzip it.</span></span>
1. <span data-ttu-id="e50e8-138">Verbinden Sie Ihre HoloLens mit ihrem PC, indem Sie ein USB-A-zu-USB-C-Kabel verwenden.</span><span class="sxs-lookup"><span data-stu-id="e50e8-138">Connect your HoloLens to your PC using a USB-A to USB-C cable.</span></span> <span data-ttu-id="e50e8-139">(Auch wenn Sie andere Kabel verwendet haben, um Ihre HoloLens zu verbinden, funktioniert dies am besten.)</span><span class="sxs-lookup"><span data-stu-id="e50e8-139">(Even if you've been using other cables to connect your HoloLens, this one works best.)</span></span>
1. <span data-ttu-id="e50e8-140">Advanced Recovery Companion erkennt Ihre HoloLens automatisch.</span><span class="sxs-lookup"><span data-stu-id="e50e8-140">The Advanced Recovery Companion automatically detects your HoloLens.</span></span> <span data-ttu-id="e50e8-141">Wählen Sie **die Microsoft HoloLens** aus.</span><span class="sxs-lookup"><span data-stu-id="e50e8-141">Select the **Microsoft HoloLens** tile.</span></span>
1. <span data-ttu-id="e50e8-142">Wählen Sie auf dem nächsten Bildschirm **Manuelle** Paketauswahl und dann die Installationsdatei aus, die in dem Ordner enthalten ist, den Sie in Schritt 4 entpackt haben.</span><span class="sxs-lookup"><span data-stu-id="e50e8-142">On the next screen, select **Manual package selection** and then select the installation file contained in the folder that you unzipped in step 4.</span></span> <span data-ttu-id="e50e8-143">(Suchen Sie nach einer Datei mit der FFU-Erweiterung.)</span><span class="sxs-lookup"><span data-stu-id="e50e8-143">(Look for a file with the .ffu extension.)</span></span>
1. <span data-ttu-id="e50e8-144">Wählen Sie **Software installieren** aus, und befolgen Sie die Anweisungen.</span><span class="sxs-lookup"><span data-stu-id="e50e8-144">Select **Install software**, and follow the instructions.</span></span>

## <a name="go-back-to-a-previous-version---hololens-1st-gen"></a><span data-ttu-id="e50e8-145">Zurück zu einer früheren Version– HoloLens (1. Generation)</span><span class="sxs-lookup"><span data-stu-id="e50e8-145">Go back to a previous version - HoloLens (1st Gen)</span></span>

<span data-ttu-id="e50e8-146">In einigen Fällen möchten Sie möglicherweise zu einer früheren Version der HoloLens-Software zurückkehren.</span><span class="sxs-lookup"><span data-stu-id="e50e8-146">In some cases, you might want to go back to a previous version of the HoloLens software.</span></span> <span data-ttu-id="e50e8-147">Hierzu können Sie das Windows Device Recovery Tool verwenden, um Ihre HoloLens auf die frühere Version zurückzusetzen.</span><span class="sxs-lookup"><span data-stu-id="e50e8-147">You can do this by using the Windows Device Recovery Tool to reset your HoloLens to the earlier version.</span></span>

> [!NOTE]
> <span data-ttu-id="e50e8-148">Wenn Sie zu einer früheren Version zurückkehren, werden Ihre persönlichen Dateien und Einstellungen gelöscht.</span><span class="sxs-lookup"><span data-stu-id="e50e8-148">Going back to an earlier version deletes your personal files and settings.</span></span>

<span data-ttu-id="e50e8-149">Führen Sie die folgenden Schritte aus, um zu einer früheren Version von HoloLens 1 zurückzukehren:</span><span class="sxs-lookup"><span data-stu-id="e50e8-149">To go back to a previous version of HoloLens 1, follow these steps:</span></span>

1. <span data-ttu-id="e50e8-150">Stellen Sie sicher, dass keine Telefone oder Windows-Geräte an Ihren PC angeschlossen sind.</span><span class="sxs-lookup"><span data-stu-id="e50e8-150">Make sure that you don't have any phones or Windows devices plugged in to your PC.</span></span>
1. <span data-ttu-id="e50e8-151">Laden Sie auf Ihrem PC das [Windows Device Recovery Tool (WDRT)](https://support.microsoft.com/help/12379)herunter.</span><span class="sxs-lookup"><span data-stu-id="e50e8-151">On your PC, download the [Windows Device Recovery Tool (WDRT)](https://support.microsoft.com/help/12379).</span></span>
1. <span data-ttu-id="e50e8-152">Laden Sie das [HoloLens Anniversary Update-Wiederherstellungspaket](https://aka.ms/hololensrecovery)herunter.</span><span class="sxs-lookup"><span data-stu-id="e50e8-152">Download the [HoloLens Anniversary Update recovery package](https://aka.ms/hololensrecovery).</span></span>
1. <span data-ttu-id="e50e8-153">Wenn die Downloads abgeschlossen sind, öffnen **Sie Den Datei-Explorer**  >  **lädt herunter.**</span><span class="sxs-lookup"><span data-stu-id="e50e8-153">When the downloads finish, open **File explorer** > **Downloads**.</span></span> <span data-ttu-id="e50e8-154">Klicken Sie mit der rechten Maustaste auf den gezippten Ordner, den Sie gerade heruntergeladen haben, und wählen **Sie Alle**  >  **extrahieren** aus, um ihn zu entzippen.</span><span class="sxs-lookup"><span data-stu-id="e50e8-154">Right-click the zipped folder you just downloaded, and select **Extract all** > **Extract** to unzip it.</span></span>
1. <span data-ttu-id="e50e8-155">Verbinden Sie Ihre HoloLens mit ihrem PC, indem Sie das micro-USB-Kabel verwenden, in dem sie installiert ist.</span><span class="sxs-lookup"><span data-stu-id="e50e8-155">Connect your HoloLens to your PC using the micro-USB cable that it came with.</span></span> <span data-ttu-id="e50e8-156">(Auch wenn Sie andere Kabel verwendet haben, um Ihre HoloLens zu verbinden, funktioniert dieses am besten.)</span><span class="sxs-lookup"><span data-stu-id="e50e8-156">(Even if you've been using other cables to connect your HoloLens, this one works best.)</span></span>
1. <span data-ttu-id="e50e8-157">Das WDRT erkennt Ihre HoloLens automatisch.</span><span class="sxs-lookup"><span data-stu-id="e50e8-157">The WDRT will automatically detect your HoloLens.</span></span> <span data-ttu-id="e50e8-158">Wählen Sie die **Kachel Microsoft HoloLens** aus.</span><span class="sxs-lookup"><span data-stu-id="e50e8-158">Select the **Microsoft HoloLens** tile.</span></span>
1. <span data-ttu-id="e50e8-159">Klicken Sie auf dem nächsten Bildschirm auf **Manuelle Paketauswahl,** und wählen Sie die Installationsdatei aus, die in dem Ordner enthalten ist, den Sie in Schritt 4 entpackt haben.</span><span class="sxs-lookup"><span data-stu-id="e50e8-159">On the next screen, select **Manual package selection** and choose the installation file contained in the folder you unzipped in step 4.</span></span> <span data-ttu-id="e50e8-160">(Suchen Sie nach einer Datei mit der FFU-Erweiterung.)</span><span class="sxs-lookup"><span data-stu-id="e50e8-160">(Look for a file with the .ffu extension.)</span></span>
1. <span data-ttu-id="e50e8-161">Wählen Sie **Software installieren** aus, und befolgen Sie die Anweisungen.</span><span class="sxs-lookup"><span data-stu-id="e50e8-161">Select **Install software**, and follow the instructions.</span></span>

> [!NOTE]
> <span data-ttu-id="e50e8-162">Wenn das WDRT Ihre HoloLens nicht erkennt, starten Sie Ihren PC neu.</span><span class="sxs-lookup"><span data-stu-id="e50e8-162">If the WDRT doesn't detect your HoloLens, try restarting your PC.</span></span> <span data-ttu-id="e50e8-163">Wenn dies nicht funktioniert, wählen Sie **Mein** Gerät wurde nicht erkannt aus, wählen Sie Microsoft HoloLens **aus,** und befolgen Sie dann die Anweisungen.</span><span class="sxs-lookup"><span data-stu-id="e50e8-163">If that doesn't work, select **My device was not detected**, select **Microsoft HoloLens**, and then follow the instructions.</span></span>

## <a name="windows-insider-program-on-hololens"></a><span data-ttu-id="e50e8-164">Windows-Insider-Programm auf HoloLens</span><span class="sxs-lookup"><span data-stu-id="e50e8-164">Windows Insider Program on HoloLens</span></span>

<span data-ttu-id="e50e8-165">Möchten Sie die neuesten Features in HoloLens sehen?</span><span class="sxs-lookup"><span data-stu-id="e50e8-165">Want to see the latest features in HoloLens?</span></span>  <span data-ttu-id="e50e8-166">Wenn ja, treten Sie dem Windows-Insider-Programm bei. Sie erhalten Zugriff auf Vorschauversionen von HoloLens-Softwareupdates, bevor sie für die allgemeine Öffentlichkeit verfügbar sind.</span><span class="sxs-lookup"><span data-stu-id="e50e8-166">If so, join the Windows Insider Program; you'll get access to preview builds of HoloLens software updates before they're available to the general public.</span></span>

<span data-ttu-id="e50e8-167">[Hier Windows-Insider Vorschauversion für Microsoft HoloLens.](hololens-insider.md)</span><span class="sxs-lookup"><span data-stu-id="e50e8-167">[Get Windows Insider preview for Microsoft HoloLens](hololens-insider.md).</span></span>
