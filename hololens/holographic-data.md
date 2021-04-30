---
title: Suchen und Speichern von Dateien auf HoloLens
description: Erfahren Sie, wie Sie den Datei-Explorer auf HoloLens verwenden, um Dateien auf Ihrem Mixed Reality-Gerät zu öffnen, anzuzeigen und zu verwalten.
keywords: Vorgehensweise, Dateiauswahl, Dateien, Fotos, Videos, Bilder, OneDrive, Speicher, Datei-Explorer, Hololens
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
ms.openlocfilehash: 2d979b2cffd20589ddef7f11db5c7206eaea23cb
ms.sourcegitcommit: ad53ba5edd567a18f0c172578d78db3190701650
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/19/2021
ms.locfileid: "108308596"
---
# <a name="find-open-and-save-files-on-hololens"></a><span data-ttu-id="b2f79-104">Suchen, Öffnen und Speichern von Dateien auf HoloLens</span><span class="sxs-lookup"><span data-stu-id="b2f79-104">Find, open, and save files on HoloLens</span></span>

<span data-ttu-id="b2f79-105">Dateien, die Sie auf HoloLens erstellen, einschließlich Fotos und Videos, werden direkt auf Ihrem HoloLens-Gerät gespeichert.</span><span class="sxs-lookup"><span data-stu-id="b2f79-105">Files you create on HoloLens, including photos and videos, are saved directly to your HoloLens device.</span></span> <span data-ttu-id="b2f79-106">Sie können sie auf die gleiche Weise anzeigen und verwalten, wie Sie Dateien auf Windows 10 verwalten würden:</span><span class="sxs-lookup"><span data-stu-id="b2f79-106">View and manage them in the same way you would manage files on Windows 10:</span></span>

- <span data-ttu-id="b2f79-107">Verwenden der Datei-Explorer-App für den Zugriff auf lokale Ordner.</span><span class="sxs-lookup"><span data-stu-id="b2f79-107">Using the File Explorer app to access local folders.</span></span>
- <span data-ttu-id="b2f79-108">Innerhalb des Speichers einer App.</span><span class="sxs-lookup"><span data-stu-id="b2f79-108">Within an app's storage.</span></span>
- <span data-ttu-id="b2f79-109">In einem speziellen Ordner (z. B. in der Video- oder Musikbibliothek).</span><span class="sxs-lookup"><span data-stu-id="b2f79-109">In a special folder (such as the video or music library).</span></span>
- <span data-ttu-id="b2f79-110">Verwenden eines Speicherdiensts, der eine App und eine Dateiauswahl enthält (z. B. OneDrive).</span><span class="sxs-lookup"><span data-stu-id="b2f79-110">Using a storage service that includes an app and file picker (such as OneDrive).</span></span>
- <span data-ttu-id="b2f79-111">Verwenden eines Mit HoloLens verbundenen Desktop-PCs über ein USB-Kabel mit MTP-Unterstützung (Media Transfer Protocol).</span><span class="sxs-lookup"><span data-stu-id="b2f79-111">Using a desktop PC connected to your HoloLens by using a USB cable, using MTP (Media Transfer Protocol) support.</span></span>

## <a name="view-files-on-hololens-using-file-explorer"></a><span data-ttu-id="b2f79-112">Anzeigen von Dateien auf HoloLens mithilfe des Datei-Explorers</span><span class="sxs-lookup"><span data-stu-id="b2f79-112">View files on HoloLens using File Explorer</span></span>

> <span data-ttu-id="b2f79-113">Gilt für alle HoloLens 2 Geräte und HoloLens (1. Generation) ab der [Windows 10 April 2018 Update (RS4) für HoloLens.](https://docs.microsoft.com/windows/mixed-reality/release-notes-april-2018)</span><span class="sxs-lookup"><span data-stu-id="b2f79-113">Applies to all HoloLens 2 devices and HoloLens (1st gen) as of the [Windows 10 April 2018 Update (RS4) for HoloLens](https://docs.microsoft.com/windows/mixed-reality/release-notes-april-2018).</span></span>

<span data-ttu-id="b2f79-114">Verwenden Sie den Datei-Explorer auf HoloLens, um Dateien auf Ihrem Gerät anzuzeigen und zu verwalten, einschließlich 3D-Objekten, Dokumenten und Bildern.</span><span class="sxs-lookup"><span data-stu-id="b2f79-114">Use File Explorer on HoloLens to view and manage files on your device, including 3D objects, documents, and pictures.</span></span> <span data-ttu-id="b2f79-115">Wechseln **Sie** zu Start   >  **Alle Apps**   >  **Datei-Explorer,** um zu beginnen.</span><span class="sxs-lookup"><span data-stu-id="b2f79-115">Go to **Start**  > **All apps**  > **File Explorer** to get started.</span></span>

> [!TIP]
> <span data-ttu-id="b2f79-116">Wenn im Datei-Explorer keine Dateien aufgeführt sind, wählen Sie im linken oberen Bereich **Dieses Gerät** aus.</span><span class="sxs-lookup"><span data-stu-id="b2f79-116">If there are no files listed in File Explorer, select **This Device** in the top left pane.</span></span>

<span data-ttu-id="b2f79-117">Wenn im Datei-Explorer keine Dateien angezeigt werden, ist der Filter "Zuletzt verwendet" möglicherweise aktiv (das Uhrsymbol ist im linken Bereich hervorgehoben).</span><span class="sxs-lookup"><span data-stu-id="b2f79-117">If you don’t see any files in File Explorer, the "Recent" filter may be active (clock icon is highlighted in left pane).</span></span> <span data-ttu-id="b2f79-118">Um dies zu beheben, wählen Sie das Dokumentsymbol **Dieses Gerät** im linken Bereich (unterhalb des Uhrsymbols) aus, oder öffnen Sie das Menü, und wählen Sie **Dieses Gerät** aus.</span><span class="sxs-lookup"><span data-stu-id="b2f79-118">To fix this, select the **This Device** document icon in the left pane (beneath the clock icon), or open the menu and select **This Device**.</span></span>

## <a name="find-and-view-your-photos-and-videos"></a><span data-ttu-id="b2f79-119">Suchen und Anzeigen Ihrer Fotos und Videos</span><span class="sxs-lookup"><span data-stu-id="b2f79-119">Find and view your photos and videos</span></span>

<span data-ttu-id="b2f79-120">[Mit Mixed Reality](holographic-photos-and-videos.md) Capture können Sie Mixed Reality-Fotos und -Videos auf HoloLens aufnehmen.</span><span class="sxs-lookup"><span data-stu-id="b2f79-120">[Mixed reality capture](holographic-photos-and-videos.md) lets you take mixed reality photos and videos on HoloLens.</span></span>  <span data-ttu-id="b2f79-121">Diese Fotos und Videos werden im Kamerarollordner des Geräts gespeichert.</span><span class="sxs-lookup"><span data-stu-id="b2f79-121">These photos and videos are saved to the device's Camera Roll folder.</span></span>

<span data-ttu-id="b2f79-122">Sie können auf Fotos und Videos zugreifen, die mit HoloLens aufgenommen wurden:</span><span class="sxs-lookup"><span data-stu-id="b2f79-122">You can access photos and videos taken with HoloLens by:</span></span>

- <span data-ttu-id="b2f79-123">Direktes Zugreifen auf die Kamerarolle über die [Fotos-App](holographic-photos-and-videos.md).</span><span class="sxs-lookup"><span data-stu-id="b2f79-123">accessing the Camera Roll directly through the [Photos app](holographic-photos-and-videos.md).</span></span>
- <span data-ttu-id="b2f79-124">Hochladen von Fotos und Videos in den Cloudspeicher durch Synchronisieren Ihrer Fotos und Videos mit OneDrive.</span><span class="sxs-lookup"><span data-stu-id="b2f79-124">uploading photos and videos to cloud storage by syncing your photos and videos to OneDrive.</span></span>
- <span data-ttu-id="b2f79-125">mithilfe Mixed Reality-Aufnahme -Seite des [Windows-Geräteportal](https://docs.microsoft.com/windows/mixed-reality/using-the-windows-device-portal#mixed-reality-capture).</span><span class="sxs-lookup"><span data-stu-id="b2f79-125">using the Mixed Reality Capture page of the [Windows Device Portal](https://docs.microsoft.com/windows/mixed-reality/using-the-windows-device-portal#mixed-reality-capture).</span></span>

### <a name="photos-app"></a><span data-ttu-id="b2f79-126">Fotos-App</span><span class="sxs-lookup"><span data-stu-id="b2f79-126">Photos app</span></span>

<span data-ttu-id="b2f79-127">Die Fotos-App ist eine der Standard-Apps im **Startmenü** und in HoloLens integriert.</span><span class="sxs-lookup"><span data-stu-id="b2f79-127">The Photos app is one of the default apps on the **Start** menu, and comes built-in with HoloLens.</span></span> <span data-ttu-id="b2f79-128">Erfahren Sie mehr über [die Verwendung der Fotos-App zum Anzeigen von Inhalten.](holographic-photos-and-videos.md)</span><span class="sxs-lookup"><span data-stu-id="b2f79-128">Learn more about [using the Photos app to view content](holographic-photos-and-videos.md).</span></span>

<span data-ttu-id="b2f79-129">Sie können die [OneDrive-App](https://www.microsoft.com/p/onedrive/9wzdncrfj1p3) auch über den Microsoft Store, um Fotos mit anderen Geräten zu synchronisieren.</span><span class="sxs-lookup"><span data-stu-id="b2f79-129">You can also install the [OneDrive app](https://www.microsoft.com/p/onedrive/9wzdncrfj1p3) from the Microsoft Store to sync photos to other devices.</span></span>

### <a name="onedrive-app"></a><span data-ttu-id="b2f79-130">OneDrive-App</span><span class="sxs-lookup"><span data-stu-id="b2f79-130">OneDrive app</span></span>

<span data-ttu-id="b2f79-131">[Mit OneDrive](https://onedrive.live.com/) können Sie auf Ihre Fotos und Videos zugreifen, diese verwalten und für beliebige Geräte und Benutzer freigeben.</span><span class="sxs-lookup"><span data-stu-id="b2f79-131">[OneDrive](https://onedrive.live.com/) lets you access, manage, and share your photos and videos with any device and with any user.</span></span> <span data-ttu-id="b2f79-132">Um auf die Fotos und Videos zu zugreifen, die auf HoloLens erfasst wurden, laden Sie die [OneDrive-App](https://www.microsoft.com/p/onedrive/9wzdncrfj1p3) aus Microsoft Store HoloLens herunter.</span><span class="sxs-lookup"><span data-stu-id="b2f79-132">To access the photos and videos captured on HoloLens, download the [OneDrive app](https://www.microsoft.com/p/onedrive/9wzdncrfj1p3) from the Microsoft Store on your HoloLens.</span></span> <span data-ttu-id="b2f79-133">Öffnen Sie nach dem Herunterladen die OneDrive-App, wählen Sie Einstellungskameraupload  >  aus, und aktivieren Sie **Kameraupload.**</span><span class="sxs-lookup"><span data-stu-id="b2f79-133">Once downloaded, open the OneDrive app and select **Settings** > **Camera upload**, and turn on **Camera upload**.</span></span>

### <a name="connect-to-a-pc"></a><span data-ttu-id="b2f79-134">Herstellen einer Verbindung mit einem PC</span><span class="sxs-lookup"><span data-stu-id="b2f79-134">Connect to a PC</span></span>

<span data-ttu-id="b2f79-135">Wenn auf Ihrer HoloLens das Update vom [Windows 10 April 2018](https://docs.microsoft.com/windows/mixed-reality/release-notes-april-2018) oder höher ausgeführt wird, können Sie Ihre HoloLens mit einem Windows 10-PC verbinden, indem Sie ein USB-Kabel verwenden, um Fotos und Videos auf dem Gerät mithilfe von MTP (Media Transfer Protocol) zu durchsuchen.</span><span class="sxs-lookup"><span data-stu-id="b2f79-135">If your HoloLens is running the [Windows 10 April 2018 update](https://docs.microsoft.com/windows/mixed-reality/release-notes-april-2018) or later, you can connect your HoloLens to a Windows 10 PC by using a USB cable to browse photos and videos on the device by using MTP (media transfer protocol).</span></span> <span data-ttu-id="b2f79-136">Sie müssen sicherstellen, dass das Gerät entsperrt ist, um Dateien zu durchsuchen, wenn Sie eine PIN oder ein Kennwort auf Ihrem Gerät eingerichtet haben.</span><span class="sxs-lookup"><span data-stu-id="b2f79-136">You'll need to make sure the device is unlocked to browse files if you have a PIN or password set up on your device.</span></span>  

<span data-ttu-id="b2f79-137">Wenn Sie die [](https://docs.microsoft.com/windows/mixed-reality/using-the-windows-device-portal)Windows-Geräteportal aktiviert haben, können Sie sie verwenden, um die auf Ihrem Gerät gespeicherten Fotos und Videos zu durchsuchen, abzurufen und zu verwalten.</span><span class="sxs-lookup"><span data-stu-id="b2f79-137">If you have enabled the [Windows Device Portal](https://docs.microsoft.com/windows/mixed-reality/using-the-windows-device-portal), you can use it to browse, retrieve, and manage the photos and videos stored on your device.</span></span>

## <a name="access-files-within-an-app"></a><span data-ttu-id="b2f79-138">Zugreifen auf Dateien in einer App</span><span class="sxs-lookup"><span data-stu-id="b2f79-138">Access files within an app</span></span>

<span data-ttu-id="b2f79-139">Wenn eine Anwendung Dateien auf Ihrem Gerät speichert, können Sie diese Anwendung verwenden, um darauf zu zugreifen.</span><span class="sxs-lookup"><span data-stu-id="b2f79-139">If an application saves files on your device, you can use that application to access them.</span></span>

### <a name="requesting-files-from-another-app"></a><span data-ttu-id="b2f79-140">Anfordern von Dateien von einer anderen App</span><span class="sxs-lookup"><span data-stu-id="b2f79-140">Requesting files from another app</span></span>

<span data-ttu-id="b2f79-141">Eine Anwendung kann mithilfe der Dateiauswahl anfordern, eine Datei zu speichern oder eine Datei aus einer anderen [App zu öffnen.](https://docs.microsoft.com/windows/mixed-reality/app-model#file-pickers)</span><span class="sxs-lookup"><span data-stu-id="b2f79-141">An application can request to save a file or open a file from another app by using [file pickers](https://docs.microsoft.com/windows/mixed-reality/app-model#file-pickers).</span></span>

### <a name="known-folders"></a><span data-ttu-id="b2f79-142">Bekannte Ordner</span><span class="sxs-lookup"><span data-stu-id="b2f79-142">Known folders</span></span>

<span data-ttu-id="b2f79-143">HoloLens unterstützt eine Reihe [bekannter Ordner,](https://docs.microsoft.com/windows/mixed-reality/app-model#known-folders) für die Apps Zugriffsberechtigungen anfordern können.</span><span class="sxs-lookup"><span data-stu-id="b2f79-143">HoloLens supports a number of [known folders](https://docs.microsoft.com/windows/mixed-reality/app-model#known-folders) that apps can request permission to access.</span></span>

## <a name="view-hololens-files-on-your-pc"></a><span data-ttu-id="b2f79-144">Anzeigen von HoloLens-Dateien auf Ihrem PC</span><span class="sxs-lookup"><span data-stu-id="b2f79-144">View HoloLens files on your PC</span></span>

<span data-ttu-id="b2f79-145">Verbinden Sie HoloLens ähnlich wie andere mobile Geräte mithilfe von MTP (Media Transfer Protocol) mit Ihrem Desktop-PC, und öffnen Sie den Datei-Explorer auf dem PC, um zur einfachen Übertragung auf Ihre HoloLens-Bibliotheken zuzugreifen.</span><span class="sxs-lookup"><span data-stu-id="b2f79-145">Similar to other mobile devices, connect HoloLens to your desktop PC using MTP (Media Transfer Protocol) and open File Explorer on the PC to access your HoloLens libraries for easy transfer.</span></span>

<span data-ttu-id="b2f79-146">So sehen Sie Ihre HoloLens-Dateien im Datei-Explorer auf Ihrem PC:</span><span class="sxs-lookup"><span data-stu-id="b2f79-146">To see your HoloLens files in File Explorer on your PC:</span></span>

1. <span data-ttu-id="b2f79-147">Melden Sie sich bei HoloLens an, und schließen Sie es dann über das USB-Kabel, das mit holoLens stammt, an den PC an.</span><span class="sxs-lookup"><span data-stu-id="b2f79-147">Sign in to HoloLens, then plug it into the PC using the USB cable that came with the HoloLens.</span></span>

1. <span data-ttu-id="b2f79-148">Wählen Sie **Gerät öffnen aus, um Dateien mit dem Datei-Explorer anzuzeigen,** oder öffnen Sie den Datei-Explorer auf dem PC, und navigieren Sie zum Gerät.</span><span class="sxs-lookup"><span data-stu-id="b2f79-148">Select **Open Device to view files with File Explorer**, or open File Explorer on the PC and navigate to the device.</span></span>

<span data-ttu-id="b2f79-149">Um Informationen zu HoloLens anzuzeigen, klicken Sie im Datei-Explorer auf Ihrem PC mit der rechten Maustaste auf den Gerätenamen, und wählen Sie dann **Eigenschaften** aus.</span><span class="sxs-lookup"><span data-stu-id="b2f79-149">To see info about your HoloLens, right-click the device name in File Explorer on your PC, then select **Properties**.</span></span>

> [!NOTE]
> <span data-ttu-id="b2f79-150">HoloLens (1. Generation) unterstützt keine Verbindung mit externen Festplatten oder SD-Karten.</span><span class="sxs-lookup"><span data-stu-id="b2f79-150">HoloLens (1st gen) does not support connecting to external hard drives or SD cards.</span></span>

## <a name="sync-to-the-cloud"></a><span data-ttu-id="b2f79-151">Synchronisieren mit der Cloud</span><span class="sxs-lookup"><span data-stu-id="b2f79-151">Sync to the cloud</span></span>

<span data-ttu-id="b2f79-152">Installieren und einrichten Sie OneDrive auf HoloLens, um Fotos und andere Dateien von HoloLens mit der Cloud zu synchronisieren.</span><span class="sxs-lookup"><span data-stu-id="b2f79-152">To sync photos and other files from your HoloLens to the cloud, install and set up OneDrive on HoloLens.</span></span> <span data-ttu-id="b2f79-153">Um OneDrive zu erhalten, suchen Sie im Microsoft Store auf Ihrer HoloLens danach.</span><span class="sxs-lookup"><span data-stu-id="b2f79-153">To get OneDrive, search for it in the Microsoft Store on your HoloLens.</span></span>

<span data-ttu-id="b2f79-154">HoloLens gesichert keine App-Dateien und -Daten. Daher ist es eine gute Idee, Ihre wichtigen Dinge in OneDrive zu speichern.</span><span class="sxs-lookup"><span data-stu-id="b2f79-154">HoloLens doesn't back up app files and data, so it's a good idea to save your important stuff to OneDrive.</span></span> <span data-ttu-id="b2f79-155">Auf diese Weise werden Ihre Informationen gesichert, wenn Sie Ihr Gerät zurücksetzen oder eine App deinstallieren.</span><span class="sxs-lookup"><span data-stu-id="b2f79-155">That way, if you reset your device or uninstall an app, your info will be backed up.</span></span>
