---
title: Aktualisieren von HoloLens
description: Überprüfen Sie die Buildnummer, das Update und die Rollback-Updates Ihres HoloLens.
keywords: Anleitung, Update, Rollback, HoloLens, Buildnummer überprüfen
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
ms.openlocfilehash: ee007b00b350ea0f80cda34964d32a57dc6dc0c6
ms.sourcegitcommit: 7c057aeeaeebb4daffa2120491d4e897a31e8d0f
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 06/26/2020
ms.locfileid: "10828056"
---
# <span data-ttu-id="04f6a-104">Aktualisieren von HoloLens</span><span class="sxs-lookup"><span data-stu-id="04f6a-104">Update HoloLens</span></span>

<span data-ttu-id="04f6a-105">HoloLens verwendet Windows Update, genau wie andere Windows 10-Geräte.</span><span class="sxs-lookup"><span data-stu-id="04f6a-105">HoloLens uses Windows Update, just like other Windows 10 devices.</span></span> <span data-ttu-id="04f6a-106">Ihr HoloLens wird System Updates automatisch herunterladen und installieren, wenn es am Stromnetz angeschlossen und mit dem Internet verbunden ist, selbst wenn es sich im Standbymodus befindet.</span><span class="sxs-lookup"><span data-stu-id="04f6a-106">Your HoloLens will automatically download and install system updates whenever it is plugged-in to power and connected to the Internet, even when it is in standby.</span></span>

<span data-ttu-id="04f6a-107">In diesem Artikel werden die HoloLens-Tools für die folgenden Schritte erläutert:</span><span class="sxs-lookup"><span data-stu-id="04f6a-107">This article will walk through HoloLens tools for:</span></span>

- <span data-ttu-id="04f6a-108">Anzeigen der aktuellen Version des Betriebssystems (Buildnummer)</span><span class="sxs-lookup"><span data-stu-id="04f6a-108">viewing your current operating system version (build number)</span></span>
- <span data-ttu-id="04f6a-109">nach Updates suchen</span><span class="sxs-lookup"><span data-stu-id="04f6a-109">checking for updates</span></span>
- <span data-ttu-id="04f6a-110">Manuelles Aktualisieren von HoloLens</span><span class="sxs-lookup"><span data-stu-id="04f6a-110">manually updating HoloLens</span></span>
- <span data-ttu-id="04f6a-111">Rollback zu einem älteren Update</span><span class="sxs-lookup"><span data-stu-id="04f6a-111">rolling back to an older update</span></span>

## <span data-ttu-id="04f6a-112">Überprüfen der Betriebssystemversion (Buildnummer)</span><span class="sxs-lookup"><span data-stu-id="04f6a-112">Check your operating system version (build number)</span></span>

<span data-ttu-id="04f6a-113">Sie können die Versionsnummer des Systems (Buildnummer) überprüfen, indem Sie die Einstellungs-APP öffnen und **System**  >  **Info**auswählen.</span><span class="sxs-lookup"><span data-stu-id="04f6a-113">You can verify the system version number, (build number) by opening the Settings app and selecting **System** > **About**.</span></span>

## <span data-ttu-id="04f6a-114">Nach Updates suchen und manuell aktualisieren</span><span class="sxs-lookup"><span data-stu-id="04f6a-114">Check for updates and manually update</span></span>

<span data-ttu-id="04f6a-115">Sie können jederzeit in den Einstellungen nach Updates suchen.</span><span class="sxs-lookup"><span data-stu-id="04f6a-115">You can check for updates any time in settings.</span></span>  <span data-ttu-id="04f6a-116">So zeigen Sie verfügbare Updates an und überprüfen auf neue Updates:</span><span class="sxs-lookup"><span data-stu-id="04f6a-116">To see available updates and check for new updates:</span></span>

1. <span data-ttu-id="04f6a-117">Öffnen Sie die APP **Einstellungen** .</span><span class="sxs-lookup"><span data-stu-id="04f6a-117">Open the **Settings** app.</span></span>
1. <span data-ttu-id="04f6a-118">Navigieren Sie zu **Update & Security**  >  **Windows Update**.</span><span class="sxs-lookup"><span data-stu-id="04f6a-118">Navigate to **Update & Security** > **Windows Update**.</span></span>
1. <span data-ttu-id="04f6a-119">Wählen Sie **nach Updates**suchen aus.</span><span class="sxs-lookup"><span data-stu-id="04f6a-119">Select **Check for updates**.</span></span>

<span data-ttu-id="04f6a-120">Wenn ein Update verfügbar ist, wird das Herunterladen der neuen Version gestartet.</span><span class="sxs-lookup"><span data-stu-id="04f6a-120">If an update is available, it will start downloading the new version.</span></span> <span data-ttu-id="04f6a-121">Nachdem der Download abgeschlossen ist, wählen Sie die Schaltfläche **jetzt neu starten** aus, um die Installation auszulösen.</span><span class="sxs-lookup"><span data-stu-id="04f6a-121">After the download is complete, select the **Restart Now** button to trigger the installation.</span></span> <span data-ttu-id="04f6a-122">Wenn Ihr Gerät unter 40% liegt und nicht angeschlossen ist, startet der Neustart nicht mehr mit der Installation des Updates.</span><span class="sxs-lookup"><span data-stu-id="04f6a-122">If your device is below 40% and not plugged in, restarting will not start installing the update.</span></span>

<span data-ttu-id="04f6a-123">Während Ihr HoloLens das Update installiert, werden Spinning Gears und eine Statusanzeige angezeigt.</span><span class="sxs-lookup"><span data-stu-id="04f6a-123">While your HoloLens is installing the update, it will display spinning gears and a progress indicator.</span></span> <span data-ttu-id="04f6a-124">Schalten Sie Ihr HoloLens während dieser Zeit nicht aus.</span><span class="sxs-lookup"><span data-stu-id="04f6a-124">Do not turn off your HoloLens during this time.</span></span> <span data-ttu-id="04f6a-125">Nachdem die Installation abgeschlossen ist, wird Sie automatisch neu gestartet.</span><span class="sxs-lookup"><span data-stu-id="04f6a-125">It will restart automatically once it has completed the installation.</span></span>

<span data-ttu-id="04f6a-126">HoloLens wendet jeweils ein Update an.</span><span class="sxs-lookup"><span data-stu-id="04f6a-126">HoloLens applies one update at a time.</span></span>  <span data-ttu-id="04f6a-127">Wenn Ihr HoloLens mehr als eine Version hinter dem neuesten Stand hat, müssen Sie möglicherweise den Updateprozess mehrmals durchlaufen, um ihn vollständig auf dem neuesten Stand zu halten.</span><span class="sxs-lookup"><span data-stu-id="04f6a-127">If your HoloLens is more than one version behind the latest you may need to run through the update process multiple times to get it fully up to date.</span></span>

## <span data-ttu-id="04f6a-128">Zurückkehren zu einer vorherigen Version-HoloLens 2</span><span class="sxs-lookup"><span data-stu-id="04f6a-128">Go back to a previous version - HoloLens 2</span></span>

<span data-ttu-id="04f6a-129">In einigen Fällen möchten Sie möglicherweise zu einer früheren Version der HoloLens-Software zurückkehren.</span><span class="sxs-lookup"><span data-stu-id="04f6a-129">In some cases, you might want to go back to a previous version of the HoloLens software.</span></span> <span data-ttu-id="04f6a-130">Verwenden Sie dazu den erweiterten Wiederherstellungs-Assistenten, um Ihre HoloLens auf die frühere Version zurückzusetzen.</span><span class="sxs-lookup"><span data-stu-id="04f6a-130">You can do this by using the Advanced Recovery Companion to reset your HoloLens to the earlier version.</span></span>

> [!NOTE]
> <span data-ttu-id="04f6a-131">Wenn Sie zu einer früheren Version zurückkehren, werden Ihre persönlichen Dateien und Einstellungen gelöscht.</span><span class="sxs-lookup"><span data-stu-id="04f6a-131">Going back to an earlier version deletes your personal files and settings.</span></span>

<span data-ttu-id="04f6a-132">Gehen Sie wie folgt vor, um zu einer früheren Version von HoloLens 2 zurückzukehren:</span><span class="sxs-lookup"><span data-stu-id="04f6a-132">To go back to a previous version of HoloLens 2, follow these steps:</span></span>

1. <span data-ttu-id="04f6a-133">Stellen Sie sicher, dass keine Telefone oder Windows-Geräte an Ihren PC angeschlossen sind.</span><span class="sxs-lookup"><span data-stu-id="04f6a-133">Make sure that you don't have any phones or Windows devices plugged in to your PC.</span></span>
1. <span data-ttu-id="04f6a-134">Laden Sie auf Ihrem PC den [Advanced Recovery Companion](https://www.microsoft.com/p/advanced-recovery-companion/9p74z35sfrs8?activetab=pivot:overviewtab) aus dem Microsoft Store herunter.</span><span class="sxs-lookup"><span data-stu-id="04f6a-134">On your PC, download the [Advanced Recovery Companion](https://www.microsoft.com/p/advanced-recovery-companion/9p74z35sfrs8?activetab=pivot:overviewtab) from the Microsoft Store.</span></span>
1. <span data-ttu-id="04f6a-135">Laden Sie die [neueste Version von HoloLens 2](https://aka.ms/hololens2download)herunter.</span><span class="sxs-lookup"><span data-stu-id="04f6a-135">Download the [most recent HoloLens 2 release](https://aka.ms/hololens2download).</span></span>
1. <span data-ttu-id="04f6a-136">Wenn Sie diese Downloads beenden, öffnen Sie **Datei-Explorer**-  >  **Downloads**.</span><span class="sxs-lookup"><span data-stu-id="04f6a-136">When you have finished these downloads, open **File explorer** > **Downloads**.</span></span> <span data-ttu-id="04f6a-137">Klicken Sie mit der rechten Maustaste auf den soeben heruntergeladenen gezippten Ordner, und wählen Sie **Alle extrahieren** > **Extrahieren** aus, um die Dateien zu entpacken.</span><span class="sxs-lookup"><span data-stu-id="04f6a-137">Right-click the zipped folder that you just downloaded, and select **Extract all** > **Extract** to unzip it.</span></span>
1. <span data-ttu-id="04f6a-138">Schließen Sie Ihr HoloLens mit einem USB-a-Kabel an Ihren PC an.</span><span class="sxs-lookup"><span data-stu-id="04f6a-138">Connect your HoloLens to your PC using a USB-A to USB-C cable.</span></span> <span data-ttu-id="04f6a-139">(Auch wenn Sie Ihre HoloLens mit anderen Kabeln verbunden haben, funktioniert dies am besten.)</span><span class="sxs-lookup"><span data-stu-id="04f6a-139">(Even if you've been using other cables to connect your HoloLens, this one works best.)</span></span>
1. <span data-ttu-id="04f6a-140">Der Advanced Recovery Companion erkennt automatisch Ihr HoloLens.</span><span class="sxs-lookup"><span data-stu-id="04f6a-140">The Advanced Recovery Companion automatically detects your HoloLens.</span></span> <span data-ttu-id="04f6a-141">Wählen Sie die Kachel **Microsoft HoloLens** aus.</span><span class="sxs-lookup"><span data-stu-id="04f6a-141">Select the **Microsoft HoloLens** tile.</span></span>
1. <span data-ttu-id="04f6a-142">Wählen Sie auf dem nächsten Bildschirm **Manuelle Paketauswahl** aus, und wählen Sie dann die Installationsdatei aus, die in dem Ordner enthalten ist, den Sie in Schritt 4 entpackt haben.</span><span class="sxs-lookup"><span data-stu-id="04f6a-142">On the next screen, select **Manual package selection** and then select the installation file contained in the folder that you unzipped in step 4.</span></span> <span data-ttu-id="04f6a-143">(Suchen Sie nach einer Datei mit der Erweiterung FFU.)</span><span class="sxs-lookup"><span data-stu-id="04f6a-143">(Look for a file with the .ffu extension.)</span></span>
1. <span data-ttu-id="04f6a-144">Wählen Sie **Software installieren**aus, und folgen Sie den Anweisungen.</span><span class="sxs-lookup"><span data-stu-id="04f6a-144">Select **Install software**, and follow the instructions.</span></span>

## <span data-ttu-id="04f6a-145">Zurückkehren zu einer vorherigen Version – HoloLens (1st Generation)</span><span class="sxs-lookup"><span data-stu-id="04f6a-145">Go back to a previous version - HoloLens (1st Gen)</span></span>

<span data-ttu-id="04f6a-146">In einigen Fällen möchten Sie möglicherweise zu einer früheren Version der HoloLens-Software zurückkehren.</span><span class="sxs-lookup"><span data-stu-id="04f6a-146">In some cases, you might want to go back to a previous version of the HoloLens software.</span></span> <span data-ttu-id="04f6a-147">Verwenden Sie dazu das Windows Device Recovery Tool, um Ihre HoloLens auf die frühere Version zurückzusetzen.</span><span class="sxs-lookup"><span data-stu-id="04f6a-147">You can do this by using the Windows Device Recovery Tool to reset your HoloLens to the earlier version.</span></span>

> [!NOTE]
> <span data-ttu-id="04f6a-148">Wenn Sie zu einer früheren Version zurückkehren, werden Ihre persönlichen Dateien und Einstellungen gelöscht.</span><span class="sxs-lookup"><span data-stu-id="04f6a-148">Going back to an earlier version deletes your personal files and settings.</span></span>

<span data-ttu-id="04f6a-149">Gehen Sie wie folgt vor, um zu einer früheren Version von HoloLens 1 zurückzukehren:</span><span class="sxs-lookup"><span data-stu-id="04f6a-149">To go back to a previous version of HoloLens 1, follow these steps:</span></span>

1. <span data-ttu-id="04f6a-150">Stellen Sie sicher, dass keine Telefone oder Windows-Geräte an Ihren PC angeschlossen sind.</span><span class="sxs-lookup"><span data-stu-id="04f6a-150">Make sure that you don't have any phones or Windows devices plugged in to your PC.</span></span>
1. <span data-ttu-id="04f6a-151">Laden Sie auf Ihrem PC das [Windows Device Recovery Tool (WDRT)](https://support.microsoft.com/help/12379)herunter.</span><span class="sxs-lookup"><span data-stu-id="04f6a-151">On your PC, download the [Windows Device Recovery Tool (WDRT)](https://support.microsoft.com/help/12379).</span></span>
1. <span data-ttu-id="04f6a-152">Laden Sie das [HoloLens Anniversary Update-Wiederherstellungs Paket](https://aka.ms/hololensrecovery)herunter.</span><span class="sxs-lookup"><span data-stu-id="04f6a-152">Download the [HoloLens Anniversary Update recovery package](https://aka.ms/hololensrecovery).</span></span>
1. <span data-ttu-id="04f6a-153">Wenn der Download abgeschlossen ist, öffnen Sie **Datei-Explorer**-  >  **Downloads**.</span><span class="sxs-lookup"><span data-stu-id="04f6a-153">When the downloads finish, open **File explorer** > **Downloads**.</span></span> <span data-ttu-id="04f6a-154">Klicken Sie mit der rechten Maustaste auf den soeben heruntergeladenen ZIP-Ordner, und wählen Sie **extrahieren**  >  **aus,** um ihn zu entpacken.</span><span class="sxs-lookup"><span data-stu-id="04f6a-154">Right-click the zipped folder you just downloaded, and select **Extract all** > **Extract** to unzip it.</span></span>
1. <span data-ttu-id="04f6a-155">Verbinden Sie Ihr HoloLens mit Ihrem PC über das Micro-USB-Kabel, mit dem es geliefert wurde.</span><span class="sxs-lookup"><span data-stu-id="04f6a-155">Connect your HoloLens to your PC using the micro-USB cable that it came with.</span></span> <span data-ttu-id="04f6a-156">(Auch wenn Sie Ihre HoloLens mit anderen Kabeln verbunden haben, funktioniert dies am besten.)</span><span class="sxs-lookup"><span data-stu-id="04f6a-156">(Even if you've been using other cables to connect your HoloLens, this one works best.)</span></span>
1. <span data-ttu-id="04f6a-157">Die WDRT erkennt Ihre HoloLens automatisch.</span><span class="sxs-lookup"><span data-stu-id="04f6a-157">The WDRT will automatically detect your HoloLens.</span></span> <span data-ttu-id="04f6a-158">Wählen Sie die Kachel **Microsoft HoloLens** aus.</span><span class="sxs-lookup"><span data-stu-id="04f6a-158">Select the **Microsoft HoloLens** tile.</span></span>
1. <span data-ttu-id="04f6a-159">Wählen Sie auf dem nächsten Bildschirm **Manuelle Paketauswahl** aus, und wählen Sie die Installationsdatei aus, die in dem Ordner enthalten ist, den Sie in Schritt 4 entpackt haben.</span><span class="sxs-lookup"><span data-stu-id="04f6a-159">On the next screen, select **Manual package selection** and choose the installation file contained in the folder you unzipped in step 4.</span></span> <span data-ttu-id="04f6a-160">(Suchen Sie nach einer Datei mit der Erweiterung FFU.)</span><span class="sxs-lookup"><span data-stu-id="04f6a-160">(Look for a file with the .ffu extension.)</span></span>
1. <span data-ttu-id="04f6a-161">Wählen Sie **Software installieren**aus, und folgen Sie den Anweisungen.</span><span class="sxs-lookup"><span data-stu-id="04f6a-161">Select **Install software**, and follow the instructions.</span></span>

> [!NOTE]
> <span data-ttu-id="04f6a-162">Wenn die WDRT ihre HoloLens nicht erkennt, versuchen Sie, Ihren PC neu zu starten.</span><span class="sxs-lookup"><span data-stu-id="04f6a-162">If the WDRT doesn't detect your HoloLens, try restarting your PC.</span></span> <span data-ttu-id="04f6a-163">Wenn dies nicht funktioniert, wählen Sie **mein Gerät wurde nicht erkannt**aus, wählen Sie **Microsoft HoloLens**aus, und folgen Sie dann den Anweisungen.</span><span class="sxs-lookup"><span data-stu-id="04f6a-163">If that doesn't work, select **My device was not detected**, select **Microsoft HoloLens**, and then follow the instructions.</span></span>

## <span data-ttu-id="04f6a-164">Windows-Insider-Programm auf HoloLens</span><span class="sxs-lookup"><span data-stu-id="04f6a-164">Windows Insider Program on HoloLens</span></span>

<span data-ttu-id="04f6a-165">Möchten Sie die neuesten Funktionen in HoloLens anzeigen?</span><span class="sxs-lookup"><span data-stu-id="04f6a-165">Want to see the latest features in HoloLens?</span></span>  <span data-ttu-id="04f6a-166">Wenn ja, nehmen Sie am Windows-Insider-Programm Teil; Sie erhalten Zugriff auf Preview-Builds von HoloLens-Softwareupdates, bevor Sie für die allgemeine Öffentlichkeit verfügbar sind.</span><span class="sxs-lookup"><span data-stu-id="04f6a-166">If so, join the Windows Insider Program; you'll get access to preview builds of HoloLens software updates before they're available to the general public.</span></span>

<span data-ttu-id="04f6a-167">[Holen Sie sich Windows Insider Preview für Microsoft HoloLens](hololens-insider.md).</span><span class="sxs-lookup"><span data-stu-id="04f6a-167">[Get Windows Insider preview for Microsoft HoloLens](hololens-insider.md).</span></span>
