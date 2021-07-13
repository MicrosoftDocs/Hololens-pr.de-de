---
title: Suchen und Speichern von Dateien auf HoloLens
description: Erfahren Sie, wie Sie den Datei-Explorer auf HoloLens, um Dateien auf Ihrem Mixed Reality-Gerät zu öffnen, zu öffnen und zu verwalten.
keywords: How-to, file picker, files, photos, videos, pictures, OneDrive, storage, file explorer, hololens
ms.assetid: 77d2e357-f65f-43c8-b62f-6cd9bf37070a
author: mattzmsft
ms.author: mazeller
manager: v-miegge
ms.reviewer: jarrettrenshaw
ms.date: 12/30/2019
ms.prod: hololens
ms.sitesec: library
ms.topic: article
audience: ITPro
ms.localizationpriority: medium
appliesto:
- HoloLens (1st gen)
- HoloLens 2
ms.openlocfilehash: 18dc962b869dafaea9ff9c605eef51fcbb35bfb2
ms.sourcegitcommit: c43cd2f450b643ad4fc8e749235d03ec5aa3ffcf
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 07/12/2021
ms.locfileid: "113636179"
---
# <a name="find-open-and-save-files-on-hololens"></a><span data-ttu-id="e4c8d-104">Suchen, Öffnen und Speichern von Dateien mit HoloLens</span><span class="sxs-lookup"><span data-stu-id="e4c8d-104">Find, open, and save files on HoloLens</span></span>

<span data-ttu-id="e4c8d-105">Dateien, die Sie auf einem HoloLens, einschließlich Fotos und Videos, werden direkt auf Ihrem HoloLens gespeichert.</span><span class="sxs-lookup"><span data-stu-id="e4c8d-105">Files you create on HoloLens, including photos and videos, are saved directly to your HoloLens device.</span></span> <span data-ttu-id="e4c8d-106">Sie können sie auf die gleiche Weise anzeigen und verwalten wie Dateien auf Windows 10:</span><span class="sxs-lookup"><span data-stu-id="e4c8d-106">View and manage them in the same way you would manage files on Windows 10:</span></span>

- <span data-ttu-id="e4c8d-107">Verwenden der Datei-Explorer-App für den Zugriff auf lokale Ordner.</span><span class="sxs-lookup"><span data-stu-id="e4c8d-107">Using the File Explorer app to access local folders.</span></span>
- <span data-ttu-id="e4c8d-108">Im Speicher einer App.</span><span class="sxs-lookup"><span data-stu-id="e4c8d-108">Within an app's storage.</span></span>
- <span data-ttu-id="e4c8d-109">In einem speziellen Ordner (z. B. in der Video- oder Musikbibliothek).</span><span class="sxs-lookup"><span data-stu-id="e4c8d-109">In a special folder (such as the video or music library).</span></span>
- <span data-ttu-id="e4c8d-110">Verwenden eines Speicherdiensts, der eine App und eine Dateiauswahl enthält (z. B. OneDrive).</span><span class="sxs-lookup"><span data-stu-id="e4c8d-110">Using a storage service that includes an app and file picker (such as OneDrive).</span></span>
- <span data-ttu-id="e4c8d-111">Verwenden eines Desktop-PCs, der HoloLens mithilfe eines USB-Kabels mit MTP-Unterstützung (Media Transfer Protocol) verbunden ist.</span><span class="sxs-lookup"><span data-stu-id="e4c8d-111">Using a desktop PC connected to your HoloLens by using a USB cable, using MTP (Media Transfer Protocol) support.</span></span>

## <a name="view-files-on-hololens-using-file-explorer"></a><span data-ttu-id="e4c8d-112">Anzeigen von Dateien auf HoloLens mithilfe des Datei-Explorers</span><span class="sxs-lookup"><span data-stu-id="e4c8d-112">View files on HoloLens using File Explorer</span></span>

> <span data-ttu-id="e4c8d-113">Gilt für alle HoloLens 2-Geräte und HoloLens (1. Generation) ab dem Update vom [Windows 10 April 2018 (RS4) für HoloLens](/windows/mixed-reality/release-notes-april-2018).</span><span class="sxs-lookup"><span data-stu-id="e4c8d-113">Applies to all HoloLens 2 devices and HoloLens (1st gen) as of the [Windows 10 April 2018 Update (RS4) for HoloLens](/windows/mixed-reality/release-notes-april-2018).</span></span>

<span data-ttu-id="e4c8d-114">Verwenden Sie den Datei-Explorer auf HoloLens, um Dateien auf Ihrem Gerät, einschließlich 3D-Objekten, Dokumenten und Bildern, anzeigen und verwalten zu können.</span><span class="sxs-lookup"><span data-stu-id="e4c8d-114">Use File Explorer on HoloLens to view and manage files on your device, including 3D objects, documents, and pictures.</span></span> <span data-ttu-id="e4c8d-115">Wechseln Sie **zu Alle Apps**   >     >  **Datei-Explorer starten,** um zu beginnen.</span><span class="sxs-lookup"><span data-stu-id="e4c8d-115">Go to **Start**  > **All apps**  > **File Explorer** to get started.</span></span>

> [!TIP]
> <span data-ttu-id="e4c8d-116">Wenn im Datei-Explorer keine Dateien aufgeführt sind, wählen Sie **im** linken oberen Bereich dieses Geräts aus.</span><span class="sxs-lookup"><span data-stu-id="e4c8d-116">If there are no files listed in File Explorer, select **This Device** in the top left pane.</span></span>

<span data-ttu-id="e4c8d-117">Wenn im Datei-Explorer keine Dateien angezeigt werden, ist der Filter "Zuletzt verwendet" möglicherweise aktiv (das Uhrsymbol ist im linken Bereich hervorgehoben).</span><span class="sxs-lookup"><span data-stu-id="e4c8d-117">If you don’t see any files in File Explorer, the "Recent" filter may be active (clock icon is highlighted in left pane).</span></span> <span data-ttu-id="e4c8d-118">Um dieses Problem  zu beheben, wählen Sie im linken Bereich (unterhalb des Uhrsymbols) das Dokumentsymbol Dieses Gerät aus, oder öffnen Sie das Menü, und wählen Sie **Dieses Gerät aus.**</span><span class="sxs-lookup"><span data-stu-id="e4c8d-118">To fix this, select the **This Device** document icon in the left pane (beneath the clock icon), or open the menu and select **This Device**.</span></span>

## <a name="find-and-view-your-photos-and-videos"></a><span data-ttu-id="e4c8d-119">Suchen und Anzeigen Ihrer Fotos und Videos</span><span class="sxs-lookup"><span data-stu-id="e4c8d-119">Find and view your photos and videos</span></span>

<span data-ttu-id="e4c8d-120">[Mit der Mixed Reality-Aufnahme](holographic-photos-and-videos.md) können Sie Mixed Reality-Fotos und -Videos auf HoloLens.</span><span class="sxs-lookup"><span data-stu-id="e4c8d-120">[Mixed reality capture](holographic-photos-and-videos.md) lets you take mixed reality photos and videos on HoloLens.</span></span>  <span data-ttu-id="e4c8d-121">Diese Fotos und Videos werden im Kamerarollordner des Geräts gespeichert.</span><span class="sxs-lookup"><span data-stu-id="e4c8d-121">These photos and videos are saved to the device's Camera Roll folder.</span></span>

<span data-ttu-id="e4c8d-122">Sie können auf Fotos und Videos zugreifen, die mit HoloLens wurden:</span><span class="sxs-lookup"><span data-stu-id="e4c8d-122">You can access photos and videos taken with HoloLens by:</span></span>

- <span data-ttu-id="e4c8d-123">Direktes Zugreifen auf camera roll über die [Fotos-App.](holographic-photos-and-videos.md)</span><span class="sxs-lookup"><span data-stu-id="e4c8d-123">accessing the Camera Roll directly through the [Photos app](holographic-photos-and-videos.md).</span></span>
- <span data-ttu-id="e4c8d-124">Hochladen von Fotos und Videos in den Cloudspeicher durch Synchronisieren Ihrer Fotos und Videos mit OneDrive.</span><span class="sxs-lookup"><span data-stu-id="e4c8d-124">uploading photos and videos to cloud storage by syncing your photos and videos to OneDrive.</span></span>
- <span data-ttu-id="e4c8d-125">mithilfe Mixed Reality-Aufnahme -Seite des [Windows Geräteportal](/windows/mixed-reality/using-the-windows-device-portal#mixed-reality-capture).</span><span class="sxs-lookup"><span data-stu-id="e4c8d-125">using the Mixed Reality Capture page of the [Windows Device Portal](/windows/mixed-reality/using-the-windows-device-portal#mixed-reality-capture).</span></span>

### <a name="photos-app"></a><span data-ttu-id="e4c8d-126">Fotos-App</span><span class="sxs-lookup"><span data-stu-id="e4c8d-126">Photos app</span></span>

<span data-ttu-id="e4c8d-127">Die Fotos-App ist eine der Standard-Apps im **Startmenü** und ist mit HoloLens.</span><span class="sxs-lookup"><span data-stu-id="e4c8d-127">The Photos app is one of the default apps on the **Start** menu, and comes built-in with HoloLens.</span></span> <span data-ttu-id="e4c8d-128">Erfahren Sie mehr über [die Verwendung der Fotos-App zum Anzeigen von Inhalten.](holographic-photos-and-videos.md)</span><span class="sxs-lookup"><span data-stu-id="e4c8d-128">Learn more about [using the Photos app to view content](holographic-photos-and-videos.md).</span></span>

<span data-ttu-id="e4c8d-129">Sie können die App auch über [OneDrive Installieren Microsoft Store,](https://www.microsoft.com/p/onedrive/9wzdncrfj1p3) um Fotos mit anderen Geräten zu synchronisieren.</span><span class="sxs-lookup"><span data-stu-id="e4c8d-129">You can also install the [OneDrive app](https://www.microsoft.com/p/onedrive/9wzdncrfj1p3) from the Microsoft Store to sync photos to other devices.</span></span>

### <a name="onedrive-app"></a><span data-ttu-id="e4c8d-130">OneDrive-App</span><span class="sxs-lookup"><span data-stu-id="e4c8d-130">OneDrive app</span></span>

<span data-ttu-id="e4c8d-131">[OneDrive](https://onedrive.live.com/) können Sie auf Ihre Fotos und Videos zugreifen, diese verwalten und für jedes Gerät und für jeden Benutzer freigeben.</span><span class="sxs-lookup"><span data-stu-id="e4c8d-131">[OneDrive](https://onedrive.live.com/) lets you access, manage, and share your photos and videos with any device and with any user.</span></span> <span data-ttu-id="e4c8d-132">Um auf die Fotos und Videos zu HoloLens, [](https://www.microsoft.com/p/onedrive/9wzdncrfj1p3) laden Sie die OneDrive-App aus dem Microsoft Store auf Ihre HoloLens.</span><span class="sxs-lookup"><span data-stu-id="e4c8d-132">To access the photos and videos captured on HoloLens, download the [OneDrive app](https://www.microsoft.com/p/onedrive/9wzdncrfj1p3) from the Microsoft Store on your HoloLens.</span></span> <span data-ttu-id="e4c8d-133">Öffnen Sie nach dem Herunterladen die OneDrive-App, wählen Sie Einstellungen   >  **Camera upload (Kameraupload)** aus, und aktivieren Sie **Camera upload (Kameraupload).**</span><span class="sxs-lookup"><span data-stu-id="e4c8d-133">Once downloaded, open the OneDrive app and select **Settings** > **Camera upload**, and turn on **Camera upload**.</span></span>

### <a name="connect-to-a-pc"></a><span data-ttu-id="e4c8d-134">Verbinden auf einen PC</span><span class="sxs-lookup"><span data-stu-id="e4c8d-134">Connect to a PC</span></span>

<span data-ttu-id="e4c8d-135">Wenn auf Ihrem HoloLens das [Update von Windows 10 April 2018](/windows/mixed-reality/release-notes-april-2018) oder höher ausgeführt wird, können Sie Ihre HoloLens mit einem Windows 10-PC verbinden, indem Sie ein USB-Kabel verwenden, um Fotos und Videos auf dem Gerät mithilfe von MTP (Media Transfer Protocol) zu durchsuchen.</span><span class="sxs-lookup"><span data-stu-id="e4c8d-135">If your HoloLens is running the [Windows 10 April 2018 update](/windows/mixed-reality/release-notes-april-2018) or later, you can connect your HoloLens to a Windows 10 PC by using a USB cable to browse photos and videos on the device by using MTP (media transfer protocol).</span></span> <span data-ttu-id="e4c8d-136">Sie müssen sicherstellen, dass das Gerät entsperrt ist, um Dateien zu durchsuchen, wenn Sie eine PIN oder ein Kennwort auf Ihrem Gerät eingerichtet haben.</span><span class="sxs-lookup"><span data-stu-id="e4c8d-136">You'll need to make sure the device is unlocked to browse files if you have a PIN or password set up on your device.</span></span>  

<span data-ttu-id="e4c8d-137">Wenn Sie die [](/windows/mixed-reality/using-the-windows-device-portal)Windows Geräteportal aktiviert haben, können Sie sie verwenden, um die auf Ihrem Gerät gespeicherten Fotos und Videos zu durchsuchen, abzurufen und zu verwalten.</span><span class="sxs-lookup"><span data-stu-id="e4c8d-137">If you have enabled the [Windows Device Portal](/windows/mixed-reality/using-the-windows-device-portal), you can use it to browse, retrieve, and manage the photos and videos stored on your device.</span></span>

## <a name="access-files-within-an-app"></a><span data-ttu-id="e4c8d-138">Zugreifen auf Dateien in einer App</span><span class="sxs-lookup"><span data-stu-id="e4c8d-138">Access files within an app</span></span>

<span data-ttu-id="e4c8d-139">Wenn eine Anwendung Dateien auf Ihrem Gerät speichert, können Sie diese Anwendung verwenden, um darauf zu zugreifen.</span><span class="sxs-lookup"><span data-stu-id="e4c8d-139">If an application saves files on your device, you can use that application to access them.</span></span>

### <a name="requesting-files-from-another-app"></a><span data-ttu-id="e4c8d-140">Anfordern von Dateien von einer anderen App</span><span class="sxs-lookup"><span data-stu-id="e4c8d-140">Requesting files from another app</span></span>

<span data-ttu-id="e4c8d-141">Eine Anwendung kann mithilfe der Dateiauswahl anfordern, eine Datei zu speichern oder eine Datei aus einer anderen [App zu öffnen.](/windows/mixed-reality/app-model#file-pickers)</span><span class="sxs-lookup"><span data-stu-id="e4c8d-141">An application can request to save a file or open a file from another app by using [file pickers](/windows/mixed-reality/app-model#file-pickers).</span></span>

### <a name="known-folders"></a><span data-ttu-id="e4c8d-142">Bekannte Ordner</span><span class="sxs-lookup"><span data-stu-id="e4c8d-142">Known folders</span></span>

<span data-ttu-id="e4c8d-143">HoloLens unterstützt eine Reihe bekannter [Ordner,](/windows/mixed-reality/app-model#known-folders) für die Apps Zugriffsberechtigungen anfordern können.</span><span class="sxs-lookup"><span data-stu-id="e4c8d-143">HoloLens supports a number of [known folders](/windows/mixed-reality/app-model#known-folders) that apps can request permission to access.</span></span>

## <a name="view-hololens-files-on-your-pc"></a><span data-ttu-id="e4c8d-144">Anzeigen HoloLens Dateien auf Ihrem PC</span><span class="sxs-lookup"><span data-stu-id="e4c8d-144">View HoloLens files on your PC</span></span>

<span data-ttu-id="e4c8d-145">Stellen Sie ähnlich wie bei anderen mobilen Geräten über MTP (Media Transfer Protocol) eine Verbindung mit Ihrem Desktop-PC HoloLens, und öffnen Sie den Datei-Explorer auf dem PC, um zur einfachen Übertragung auf Ihre HoloLens-Bibliotheken zu zugreifen.</span><span class="sxs-lookup"><span data-stu-id="e4c8d-145">Similar to other mobile devices, connect HoloLens to your desktop PC using MTP (Media Transfer Protocol) and open File Explorer on the PC to access your HoloLens libraries for easy transfer.</span></span>

<span data-ttu-id="e4c8d-146">So sehen Sie HoloLens Dateien im Datei-Explorer auf Ihrem PC:</span><span class="sxs-lookup"><span data-stu-id="e4c8d-146">To see your HoloLens files in File Explorer on your PC:</span></span>

1. <span data-ttu-id="e4c8d-147">Melden Sie sich bei HoloLens an, und schließen Sie es dann mithilfe des USB-Kabels an den PC an, das im HoloLens.</span><span class="sxs-lookup"><span data-stu-id="e4c8d-147">Sign in to HoloLens, then plug it into the PC using the USB cable that came with the HoloLens.</span></span>

1. <span data-ttu-id="e4c8d-148">Wählen **Sie Gerät öffnen aus, um Dateien mit dem Datei-Explorer anzeigen,** oder öffnen Sie den Datei-Explorer auf dem PC, und navigieren Sie zum Gerät.</span><span class="sxs-lookup"><span data-stu-id="e4c8d-148">Select **Open Device to view files with File Explorer**, or open File Explorer on the PC and navigate to the device.</span></span>

<span data-ttu-id="e4c8d-149">Um Informationen zu Ihrer HoloLens, klicken Sie mit der rechten Maustaste auf den Gerätenamen im Datei-Explorer auf Ihrem PC, und wählen Sie dann **Eigenschaften aus.**</span><span class="sxs-lookup"><span data-stu-id="e4c8d-149">To see info about your HoloLens, right-click the device name in File Explorer on your PC, then select **Properties**.</span></span>

> [!NOTE]
> <span data-ttu-id="e4c8d-150">HoloLens (1. Generation) unterstützt keine Verbindung mit externen Festplatten oder SD-Karten.</span><span class="sxs-lookup"><span data-stu-id="e4c8d-150">HoloLens (1st gen) does not support connecting to external hard drives or SD cards.</span></span>

## <a name="sync-to-the-cloud"></a><span data-ttu-id="e4c8d-151">Synchronisieren mit der Cloud</span><span class="sxs-lookup"><span data-stu-id="e4c8d-151">Sync to the cloud</span></span>

<span data-ttu-id="e4c8d-152">Um Fotos und andere Dateien aus Ihrem HoloLens in die Cloud zu synchronisieren, installieren und richten Sie OneDrive auf HoloLens.</span><span class="sxs-lookup"><span data-stu-id="e4c8d-152">To sync photos and other files from your HoloLens to the cloud, install and set up OneDrive on HoloLens.</span></span> <span data-ttu-id="e4c8d-153">Um die OneDrive zu erhalten, suchen Sie im Microsoft Store im HoloLens.</span><span class="sxs-lookup"><span data-stu-id="e4c8d-153">To get OneDrive, search for it in the Microsoft Store on your HoloLens.</span></span>

<span data-ttu-id="e4c8d-154">HoloLens keine App-Dateien und -Daten sichern, ist es daher eine gute Idee, Ihre wichtigen Daten zu OneDrive.</span><span class="sxs-lookup"><span data-stu-id="e4c8d-154">HoloLens doesn't back up app files and data, so it's a good idea to save your important stuff to OneDrive.</span></span> <span data-ttu-id="e4c8d-155">Auf diese Weise werden Ihre Informationen gespeichert, wenn Sie Ihr Gerät zurücksetzen oder eine App deinstallieren.</span><span class="sxs-lookup"><span data-stu-id="e4c8d-155">That way, if you reset your device or uninstall an app, your info will be backed up.</span></span>
