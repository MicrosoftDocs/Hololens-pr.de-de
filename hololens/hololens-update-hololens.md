---
title: Update HoloLens 2
description: Erfahren Sie, wie Sie Ihre HoloLens-Buildnummer überprüfen, mit Geräteupdates auf dem Laufenden bleiben, am Insider-Programm teilnehmen und ein Rollback für Updates erstellen.
keywords: How-to, update, rollback, HoloLens, check build, build number
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
- HoloLens 2
ms.openlocfilehash: a27eb1d5eb32a6654f60aac98090cba1aab529d3
ms.sourcegitcommit: d5b2080868d6b74169a1bab2c7bad37dfa5a8b5a
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 06/25/2021
ms.locfileid: "112924110"
---
# <a name="update-hololens-2"></a><span data-ttu-id="7d731-104">Update HoloLens 2</span><span class="sxs-lookup"><span data-stu-id="7d731-104">Update HoloLens 2</span></span>

<span data-ttu-id="7d731-105">HoloLens verwendet Windows Update, genau wie andere Windows 10 Geräte.</span><span class="sxs-lookup"><span data-stu-id="7d731-105">HoloLens uses Windows Update, just like other Windows 10 devices.</span></span> <span data-ttu-id="7d731-106">Ihre HoloLens wird automatisch Systemupdates herunterladen und installieren, wenn sie an die Stromversorgung angeschlossen und mit dem Internet verbunden ist, auch wenn sie sich im Standbymodus befindet.</span><span class="sxs-lookup"><span data-stu-id="7d731-106">Your HoloLens will automatically download and install system updates whenever it is plugged-in to power and connected to the Internet, even when it is in standby.</span></span>

<span data-ttu-id="7d731-107">In diesem Artikel werden die HoloLens-Tools für:</span><span class="sxs-lookup"><span data-stu-id="7d731-107">This article will walk through HoloLens tools for:</span></span>

- <span data-ttu-id="7d731-108">Anzeigen ihrer aktuellen Betriebssystemversion (Buildnummer)</span><span class="sxs-lookup"><span data-stu-id="7d731-108">viewing your current operating system version (build number)</span></span>
- <span data-ttu-id="7d731-109">Suchen nach Updates</span><span class="sxs-lookup"><span data-stu-id="7d731-109">checking for updates</span></span>
- <span data-ttu-id="7d731-110">Manuelles Aktualisieren von HoloLens</span><span class="sxs-lookup"><span data-stu-id="7d731-110">manually updating HoloLens</span></span>
- <span data-ttu-id="7d731-111">Roll back to a older update (Roll back zu einem älteren Update)</span><span class="sxs-lookup"><span data-stu-id="7d731-111">rolling back to an older update</span></span>

## <a name="check-your-operating-system-version-build-number"></a><span data-ttu-id="7d731-112">Überprüfen Ihrer Betriebssystemversion (Buildnummer)</span><span class="sxs-lookup"><span data-stu-id="7d731-112">Check your operating system version (build number)</span></span>

<span data-ttu-id="7d731-113">Sie können die Systemversionsnummer (Buildnummer) überprüfen, indem Sie die App Einstellungen öffnen und **System about**  >  **auswählen.**</span><span class="sxs-lookup"><span data-stu-id="7d731-113">You can verify the system version number, (build number) by opening the Settings app and selecting **System** > **About**.</span></span>

## <a name="check-for-updates-and-manually-update"></a><span data-ttu-id="7d731-114">Suchen nach Updates und manuelles Aktualisieren</span><span class="sxs-lookup"><span data-stu-id="7d731-114">Check for updates and manually update</span></span>

<span data-ttu-id="7d731-115">Sie können jederzeit in den Einstellungen nach Updates suchen.</span><span class="sxs-lookup"><span data-stu-id="7d731-115">You can check for updates any time in settings.</span></span>  <span data-ttu-id="7d731-116">So sehen Sie verfügbare Updates und suchen nach neuen Updates:</span><span class="sxs-lookup"><span data-stu-id="7d731-116">To see available updates and check for new updates:</span></span>

1. <span data-ttu-id="7d731-117">Öffnen Sie die App **Einstellungen**.</span><span class="sxs-lookup"><span data-stu-id="7d731-117">Open the **Settings** app.</span></span>
1. <span data-ttu-id="7d731-118">Navigieren Sie **zu Update & Security**  >  **Windows Update**.</span><span class="sxs-lookup"><span data-stu-id="7d731-118">Navigate to **Update & Security** > **Windows Update**.</span></span>
1. <span data-ttu-id="7d731-119">Wählen Sie **Nach Updates suchen** aus.</span><span class="sxs-lookup"><span data-stu-id="7d731-119">Select **Check for updates**.</span></span>

<span data-ttu-id="7d731-120">Wenn ein Update verfügbar ist, wird mit dem Herunterladen der neuen Version gestartet.</span><span class="sxs-lookup"><span data-stu-id="7d731-120">If an update is available, it will start downloading the new version.</span></span> <span data-ttu-id="7d731-121">Wählen Sie nach Abschluss des Downloads die Schaltfläche **Jetzt neu starten** aus, um die Installation auszulösen.</span><span class="sxs-lookup"><span data-stu-id="7d731-121">After the download is complete, select the **Restart Now** button to trigger the installation.</span></span> <span data-ttu-id="7d731-122">Wenn Ihr Gerät unter 40 % liegt und nicht angeschlossen ist, beginnt der Neustart nicht mit der Installation des Updates.</span><span class="sxs-lookup"><span data-stu-id="7d731-122">If your device is below 40% and not plugged in, restarting will not start installing the update.</span></span>

<span data-ttu-id="7d731-123">Während Ihre HoloLens das Update installiert, werden spinnende Zahnrad und eine Statusanzeige angezeigt.</span><span class="sxs-lookup"><span data-stu-id="7d731-123">While your HoloLens is installing the update, it will display spinning gears and a progress indicator.</span></span> <span data-ttu-id="7d731-124">Deaktivieren Sie Ihre HoloLens während dieser Zeit nicht.</span><span class="sxs-lookup"><span data-stu-id="7d731-124">Do not turn off your HoloLens during this time.</span></span> <span data-ttu-id="7d731-125">Er wird automatisch neu gestartet, sobald die Installation abgeschlossen ist.</span><span class="sxs-lookup"><span data-stu-id="7d731-125">It will restart automatically once it has completed the installation.</span></span>

<span data-ttu-id="7d731-126">HoloLens wendet ein Update nach dem anderen an.</span><span class="sxs-lookup"><span data-stu-id="7d731-126">HoloLens applies one update at a time.</span></span>  <span data-ttu-id="7d731-127">Wenn Ihre HoloLens mehr als eine Version hinter der neuesten version liegt, müssen Sie den Updateprozess möglicherweise mehrmals ausführen, um ihn vollständig auf dem neuesten Stand zu halten.</span><span class="sxs-lookup"><span data-stu-id="7d731-127">If your HoloLens is more than one version behind the latest you may need to run through the update process multiple times to get it fully up to date.</span></span>

## <a name="go-back-to-a-previous-version"></a><span data-ttu-id="7d731-128">Zurück zu einer früheren Version</span><span class="sxs-lookup"><span data-stu-id="7d731-128">Go back to a previous version</span></span>

<span data-ttu-id="7d731-129">In einigen Fällen sollten Sie zu einer früheren Version der HoloLens-Software zurückkommen.</span><span class="sxs-lookup"><span data-stu-id="7d731-129">In some cases, you might want to go back to a previous version of the HoloLens software.</span></span> <span data-ttu-id="7d731-130">Die folgenden Schritte werden empfohlen:</span><span class="sxs-lookup"><span data-stu-id="7d731-130">The recommended steps are:</span></span>

1. <span data-ttu-id="7d731-131">Wenden Sie sich an den Support, um zu erfahren, ob er Ihr Problem beheben kann.</span><span class="sxs-lookup"><span data-stu-id="7d731-131">Contact Support to see if they can fix your issue.</span></span>
    1. <span data-ttu-id="7d731-132">Stellen Sie **sicher, dass** **optionale** oder vollständige Telemetrie aktiviert ist. Dadurch wird Ihr Fehler umsetzbarer und einfacher für Techniker zu diagnostizieren.</span><span class="sxs-lookup"><span data-stu-id="7d731-132">Ensure that **Optional** or **Full** telemetry is enabled -  this makes your bug more actionable and easier for engineers to diagnose.</span></span>
    1. <span data-ttu-id="7d731-133">[Das Feedback zur](hololens-feedback.md) Datei ist so beschreibend wie möglich.</span><span class="sxs-lookup"><span data-stu-id="7d731-133">[File Feedback](hololens-feedback.md) being as descriptive as possible.</span></span> <span data-ttu-id="7d731-134">Notieren Sie sich den Titel, oder verwenden Sie das Freigabefeature, damit Sie Ihren Fehler für den Support freigeben können.</span><span class="sxs-lookup"><span data-stu-id="7d731-134">Take note of the title or use the share feature so you can share your bug with Support.</span></span>
    1. <span data-ttu-id="7d731-135">Wenden Sie [sich an den Support.](https://aka.ms/hlsupport)</span><span class="sxs-lookup"><span data-stu-id="7d731-135">Contact [Support](https://aka.ms/hlsupport).</span></span> <span data-ttu-id="7d731-136">Wenn Ihr Problem gelöst werden muss, indem sie zu einer früheren Version zurückkehren, können sie Ihnen die FFU zum Flashen Ihres Geräts zur Verfügung geben.</span><span class="sxs-lookup"><span data-stu-id="7d731-136">If your issue is one that needs to be solved by returning to a previous version, they can supply you the FFU to flash your device.</span></span>

1. <span data-ttu-id="7d731-137">Wenn dies nicht funktioniert, setzen Sie Ihre Daten zurück, oder geben Sie HoloLens 2 [Advanced Recovery Companion erneut aus.](hololens-recovery.md)</span><span class="sxs-lookup"><span data-stu-id="7d731-137">If that does not work, then [reset or reflash your HoloLens 2 with the Advanced Recovery Companion](hololens-recovery.md).</span></span>
    1. <span data-ttu-id="7d731-138">Laden Sie auf Ihrem PC den [Advanced Recovery Companion aus](https://www.microsoft.com/p/advanced-recovery-companion/9p74z35sfrs8?activetab=pivot:overviewtab) dem Microsoft Store.</span><span class="sxs-lookup"><span data-stu-id="7d731-138">On your PC, download the [Advanced Recovery Companion](https://www.microsoft.com/p/advanced-recovery-companion/9p74z35sfrs8?activetab=pivot:overviewtab) from the Microsoft Store.</span></span>
    1. <span data-ttu-id="7d731-139">Stellen Sie sicher, dass keine Smartphones oder Windows-Geräte an Ihren PC angeschlossen sind.</span><span class="sxs-lookup"><span data-stu-id="7d731-139">Make sure that you don't have any phones or Windows devices plugged in to your PC.</span></span>
    1. <span data-ttu-id="7d731-140">Wählen Sie aus, für welche Version Sie flashen möchten:</span><span class="sxs-lookup"><span data-stu-id="7d731-140">Choose which version you want to flash to:</span></span>
        1. <span data-ttu-id="7d731-141">Sie können die [neueste Version HoloLens 2 herunterladen.](https://aka.ms/hololens2download)</span><span class="sxs-lookup"><span data-stu-id="7d731-141">You can download the [most recent HoloLens 2 release](https://aka.ms/hololens2download).</span></span>
        1. <span data-ttu-id="7d731-142">Sie können den Standard-Build verwenden, den ARC hostet.</span><span class="sxs-lookup"><span data-stu-id="7d731-142">You can use the default build that ARC hosts.</span></span> <span data-ttu-id="7d731-143">(Wenn Sie diese Option auswählen, überspringen Sie den nächsten Schritt.)</span><span class="sxs-lookup"><span data-stu-id="7d731-143">(If you choose this option skip the next step.)</span></span>
        1. <span data-ttu-id="7d731-144">Sie können einen Buildsupport verwenden, der Ihnen zur Verfügung gestellt wird.</span><span class="sxs-lookup"><span data-stu-id="7d731-144">You can use a build Support provided you with.</span></span>
    1. <span data-ttu-id="7d731-145">Wenn Sie diese Downloads abgeschlossen haben, öffnen Sie **Datei-Explorer**  >  **Downloads**.</span><span class="sxs-lookup"><span data-stu-id="7d731-145">When you have finished these downloads, open **File Explorer** > **Downloads**.</span></span> <span data-ttu-id="7d731-146">Klicken Sie mit der rechten Maustaste auf den zip-Ordner, den Sie gerade heruntergeladen haben, und wählen Sie **Alle** extrahieren  >  **aus,** um ihn zu entzippen.</span><span class="sxs-lookup"><span data-stu-id="7d731-146">Right-click the zipped folder that you just downloaded, and select **Extract all** > **Extract** to unzip it.</span></span>
    1. <span data-ttu-id="7d731-147">Verbinden Sie Ihre HoloLens mit ihrem PC, indem Sie ein USB-A-zu-USB-C-Kabel verwenden.</span><span class="sxs-lookup"><span data-stu-id="7d731-147">Connect your HoloLens to your PC using a USB-A to USB-C cable.</span></span> <span data-ttu-id="7d731-148">(Auch wenn Sie andere Kabel verwendet haben, um Ihre HoloLens zu verbinden, funktioniert dies am besten.)</span><span class="sxs-lookup"><span data-stu-id="7d731-148">(Even if you've been using other cables to connect your HoloLens, this one works best.)</span></span>
    1. <span data-ttu-id="7d731-149">Advanced Recovery Companion erkennt Ihre HoloLens automatisch.</span><span class="sxs-lookup"><span data-stu-id="7d731-149">The Advanced Recovery Companion automatically detects your HoloLens.</span></span> <span data-ttu-id="7d731-150">Wählen Sie **die Microsoft HoloLens** aus.</span><span class="sxs-lookup"><span data-stu-id="7d731-150">Select the **Microsoft HoloLens** tile.</span></span>
    1. <span data-ttu-id="7d731-151">Wählen Sie auf dem nächsten Bildschirm **Manuelle** Paketauswahl und dann die Installationsdatei aus, die in dem Ordner enthalten ist, den Sie in Schritt 4 entpackt haben.</span><span class="sxs-lookup"><span data-stu-id="7d731-151">On the next screen, select **Manual package selection** and then select the installation file contained in the folder that you unzipped in step 4.</span></span> <span data-ttu-id="7d731-152">(Suchen Sie nach einer Datei mit der Erweiterung .ffu.)</span><span class="sxs-lookup"><span data-stu-id="7d731-152">(Look for a file with the .ffu extension.)</span></span>
    1. <span data-ttu-id="7d731-153">Wählen **Sie Software installieren** aus, und befolgen Sie die Anweisungen.</span><span class="sxs-lookup"><span data-stu-id="7d731-153">Select **Install software**, and follow the instructions.</span></span>

> [!NOTE]
> <span data-ttu-id="7d731-154">Wenn Sie zu einer früheren Version zurückkommen, werden Ihre persönlichen Dateien und Einstellungen gelöscht.</span><span class="sxs-lookup"><span data-stu-id="7d731-154">Going back to an earlier version deletes your personal files and settings.</span></span>

<span data-ttu-id="7d731-155">Wenn Sie das derzeit installierte Release weiterhin verwenden möchten, können Sie Updates auch [manuell anhalten.](hololens-updates.md#pause-updates-via-device)</span><span class="sxs-lookup"><span data-stu-id="7d731-155">Additionally, if you would like to stay on your currently installed release, you can also manually [pause updates](hololens-updates.md#pause-updates-via-device).</span></span> <span data-ttu-id="7d731-156">Dies gibt dem Engineering-Team Zeit, das Problem zu beheben.</span><span class="sxs-lookup"><span data-stu-id="7d731-156">This will give the Engineering Team time to fix the issue.</span></span>

## <a name="windows-insider-program-on-hololens"></a><span data-ttu-id="7d731-157">Windows-Insider-Programm auf HoloLens</span><span class="sxs-lookup"><span data-stu-id="7d731-157">Windows Insider Program on HoloLens</span></span>

<span data-ttu-id="7d731-158">Möchten Sie die neuesten Features in HoloLens sehen?</span><span class="sxs-lookup"><span data-stu-id="7d731-158">Want to see the latest features in HoloLens?</span></span>  <span data-ttu-id="7d731-159">Wenn ja, treten Sie dem Windows-Insider-Programm bei. Sie erhalten Zugriff auf Vorschauversionen von HoloLens-Softwareupdates, bevor sie für die allgemeine Öffentlichkeit verfügbar sind.</span><span class="sxs-lookup"><span data-stu-id="7d731-159">If so, join the Windows Insider Program; you'll get access to preview builds of HoloLens software updates before they're available to the general public.</span></span>

<span data-ttu-id="7d731-160">[Hier Windows-Insider Vorschauversion für Microsoft HoloLens.](hololens-insider.md)</span><span class="sxs-lookup"><span data-stu-id="7d731-160">[Get Windows Insider preview for Microsoft HoloLens](hololens-insider.md).</span></span>
