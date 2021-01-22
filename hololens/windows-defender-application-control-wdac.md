---
title: Windows Defender Application Control – WDAC
description: Übersicht darüber, was Windows Defender A0 ist und wie sie zum Verwalten von Mixed -Reality-HoloLens-Geräten verwendet wird.
ms.prod: hololens
ms.sitesec: library
author: evmill
ms.author: v-evmill
ms.topic: article
ms.localizationpriority: medium
ms.date: 10/26/2020
ms.reviewer: ''
manager: yannisle
appliesto:
- HoloLens 2
ms.openlocfilehash: 23c9a274387424e8f084a4729ee621e130820716
ms.sourcegitcommit: d20057957aa05c025c9838119cc29264bc57b4bd
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 01/21/2021
ms.locfileid: "11284136"
---
# <span data-ttu-id="539a4-103">Windows Defender Application Control – WDAC</span><span class="sxs-lookup"><span data-stu-id="539a4-103">Windows Defender Application Control - WDAC</span></span>

<span data-ttu-id="539a4-104">WDAC ermöglicht einem IT-Administrator, seine Geräte so zu konfigurieren, dass das Starten von Apps auf Geräten blockiert wird.</span><span class="sxs-lookup"><span data-stu-id="539a4-104">WDAC allows an IT Admin to configure their devices to block the launch of apps on devices.</span></span> <span data-ttu-id="539a4-105">Dies ist anders als Methoden zur Geräteeinschränkung wie z. B. der Kioskmodus, bei dem dem Benutzer eine Benutzeroberfläche angezeigt wird, die die Apps auf dem Gerät ausblendet, aber dennoch gestartet werden kann.</span><span class="sxs-lookup"><span data-stu-id="539a4-105">This is different than methods of device restriction such as Kiosk mode, where  the user is presented with a UI that hides the apps on the device but they can still be launched.</span></span> <span data-ttu-id="539a4-106">Während WDAC implementiert ist, sind die Apps weiterhin in der Liste "Alle Apps" sichtbar, aber WDAC verhindert, dass diese Apps und Prozesse vom Gerätebenutzer gestartet werden können.</span><span class="sxs-lookup"><span data-stu-id="539a4-106">While WDAC is implemented, the apps are still visible in the All Apps list but WDAC stops those apps and processes from being able to be launched by the device user.</span></span>

<span data-ttu-id="539a4-107">Einem Gerät können mehrere WDAC-Richtlinien zugewiesen werden.</span><span class="sxs-lookup"><span data-stu-id="539a4-107">A device may be assigned more than one WDAC policy.</span></span> <span data-ttu-id="539a4-108">Wenn mehrere WDAC-Richtlinien auf einem System festgelegt sind, werden die restriktivsten wirksam.</span><span class="sxs-lookup"><span data-stu-id="539a4-108">If multiple WDAC policies are set on a system, most restrictive ones take effect.</span></span> 

> [!NOTE]
> <span data-ttu-id="539a4-109">Wenn Endbenutzer versuchen, eine von WDAC blockierte App zu starten, erhalten sie auf HoloLens keine Benachrichtigung darüber, dass sie diese App nicht starten können.</span><span class="sxs-lookup"><span data-stu-id="539a4-109">When end users attempt to launch an app that is blocked by WDAC, on HoloLens they will not receive a notification about not being able to launch that app.</span></span>

<span data-ttu-id="539a4-110">Im folgenden Leitfaden erfahren Benutzer, wie Sie WDAC und Windows PowerShell verwenden, um Apps auf [HoloLens 2-Geräten](https://docs.microsoft.com/mem/intune/configuration/custom-profile-hololens)mit Microsoft Intune zu erlauben oder zu blockieren.</span><span class="sxs-lookup"><span data-stu-id="539a4-110">The following is a guide for users to learn how to [use WDAC and Windows PowerShell to allow or block apps on HoloLens 2 devices with Microsoft Intune](https://docs.microsoft.com/mem/intune/configuration/custom-profile-hololens).</span></span>

<span data-ttu-id="539a4-111">Wenn Benutzer mithilfe des ersten Beispielschritts nach Apps suchen, die auf ihrem Windows 10-PC installiert sind, müssen sie möglicherweise einige Versuche zur Einschr nkung der Ergebnisse machen.</span><span class="sxs-lookup"><span data-stu-id="539a4-111">When users search for apps installed on their Windows 10 PC using the first example step, they may need to make a few attempts to narrow down the results.</span></span>

```powershell
$package1 = Get-AppxPackage -name *<applicationname>*
``` 

<span data-ttu-id="539a4-112">Wenn Sie den vollständigen Namen des Pakets nicht kennen, müssen Sie möglicherweise mehrmals "Get-AppxPackage -name \*YourBestGuess\*" ausführen, um es zu finden.</span><span class="sxs-lookup"><span data-stu-id="539a4-112">If you don’t know the full name of the package, you may need to run ‘Get-AppxPackage -name \*YourBestGuess\*’ a few times to find it.</span></span> <span data-ttu-id="539a4-113">Führen Sie dann nach dem Namen "$package 1 = Get-AppxPackage -name Actual.PackageName" aus.</span><span class="sxs-lookup"><span data-stu-id="539a4-113">Then once you have the name run ‘$package1 = Get-AppxPackage -name Actual.PackageName‘</span></span>

<span data-ttu-id="539a4-114">Wenn Sie z. B. den folgenden Namen für Microsoft Edge ausführen, werden mehr als ein Ergebnis zurückgeben, aber aus dieser Liste können Sie erkennen, dass der vollständige Name, den Sie benötigen, "Microsoft.MicrosoftEdge" ist.</span><span class="sxs-lookup"><span data-stu-id="539a4-114">For example running the following for Microsoft Edge will return more than one result, but from that list you can identify that the full name you need is Microsoft.MicrosoftEdge.</span></span>

```powershell
Get-AppxPackage -name *edge*
``` 

## <span data-ttu-id="539a4-115">Paketfamiliennamen für Apps auf HoloLens</span><span class="sxs-lookup"><span data-stu-id="539a4-115">Package Family Names for apps on HoloLens</span></span>

<span data-ttu-id="539a4-116">In dem oben verknüpften Handbuch können Sie die newPolicy.xml manuell bearbeiten und Regeln für Anwendungen hinzufügen, die nur auf HoloLens mit ihren Paketfamiliennamen installiert sind.</span><span class="sxs-lookup"><span data-stu-id="539a4-116">In the guide linked above, you can manually edit newPolicy.xml and add rules for applications that are only installed on HoloLens with their package family names.</span></span> <span data-ttu-id="539a4-117">Manchmal gibt es Apps, die Sie möglicherweise verwenden, die sich nicht auf Ihrem Desktop-PC befinden, die Sie der Richtlinie hinzufügen möchten.</span><span class="sxs-lookup"><span data-stu-id="539a4-117">Sometimes there are apps you may use to use that are not on your desktop PC that you wish to add to policy.</span></span>

<span data-ttu-id="539a4-118">Hier ist eine Liste der häufig verwendeten und In-Box für HoloLens 2-Geräte.</span><span class="sxs-lookup"><span data-stu-id="539a4-118">Here is a list of commonly used and In-Box apps for HoloLens 2 devices.</span></span>

| <span data-ttu-id="539a4-119">App-Name</span><span class="sxs-lookup"><span data-stu-id="539a4-119">App Name</span></span>                   | <span data-ttu-id="539a4-120">Paketfamilienname</span><span class="sxs-lookup"><span data-stu-id="539a4-120">Package Family Name</span></span>                                |
|----------------------------|----------------------------------------------------|
| <span data-ttu-id="539a4-121">3D-Viewer</span><span class="sxs-lookup"><span data-stu-id="539a4-121">3D Viewer</span></span>                  | <span data-ttu-id="539a4-122">Microsoft.Microsoft3DViewer_8wekyb3d8bbwe</span><span class="sxs-lookup"><span data-stu-id="539a4-122">Microsoft.Microsoft3DViewer_8wekyb3d8bbwe</span></span>          |
| <span data-ttu-id="539a4-123">App-Installer</span><span class="sxs-lookup"><span data-stu-id="539a4-123">App Installer</span></span>              | <span data-ttu-id="539a4-124">Microsoft.DesktopAppInstaller_8wekyb3d8bbwe <sup> 1</span><span class="sxs-lookup"><span data-stu-id="539a4-124">Microsoft.DesktopAppInstaller_8wekyb3d8bbwe <sup>1</span></span></sup>         |
| <span data-ttu-id="539a4-125">Calendar</span><span class="sxs-lookup"><span data-stu-id="539a4-125">Calendar</span></span>                   | <span data-ttu-id="539a4-126">microsoft.windowscommunicationsapps_8wekyb3d8bbwe</span><span class="sxs-lookup"><span data-stu-id="539a4-126">microsoft.windowscommunicationsapps_8wekyb3d8bbwe</span></span>  |
| <span data-ttu-id="539a4-127">Kamera</span><span class="sxs-lookup"><span data-stu-id="539a4-127">Camera</span></span>                     | <span data-ttu-id="539a4-128">HoloCamera_cw5n1h2txyewy</span><span class="sxs-lookup"><span data-stu-id="539a4-128">HoloCamera_cw5n1h2txyewy</span></span>                           |
| <span data-ttu-id="539a4-129">Cortana</span><span class="sxs-lookup"><span data-stu-id="539a4-129">Cortana</span></span>                    | <span data-ttu-id="539a4-130">Microsoft.549981C3F5F10_8wekyb3d8bbwe</span><span class="sxs-lookup"><span data-stu-id="539a4-130">Microsoft.549981C3F5F10_8wekyb3d8bbwe</span></span>              |
| <span data-ttu-id="539a4-131">Dynamics 365 Guides</span><span class="sxs-lookup"><span data-stu-id="539a4-131">Dynamics 365 Guides</span></span>        | <span data-ttu-id="539a4-132">Microsoft.Dynamics365.Guides_8wekyb3d8bbwe</span><span class="sxs-lookup"><span data-stu-id="539a4-132">Microsoft.Dynamics365.Guides_8wekyb3d8bbwe</span></span>         |
| <span data-ttu-id="539a4-133">Dynamics 365 Remote Assist</span><span class="sxs-lookup"><span data-stu-id="539a4-133">Dynamics 365 Remote Assist</span></span> | <span data-ttu-id="539a4-134">Microsoft.MicrosoftRemoteAssist_8wekyb3d8bbwe</span><span class="sxs-lookup"><span data-stu-id="539a4-134">Microsoft.MicrosoftRemoteAssist_8wekyb3d8bbwe</span></span>      |
| <span data-ttu-id="539a4-135">Feedback-Hub</span><span class="sxs-lookup"><span data-stu-id="539a4-135">Feedback Hub</span></span>               | <span data-ttu-id="539a4-136">Microsoft.WindowsFeedbackHub_8wekyb3d8bbwe</span><span class="sxs-lookup"><span data-stu-id="539a4-136">Microsoft.WindowsFeedbackHub_8wekyb3d8bbwe</span></span>         |
| <span data-ttu-id="539a4-137">Datei-Explorer</span><span class="sxs-lookup"><span data-stu-id="539a4-137">File Explorer</span></span>              | <span data-ttu-id="539a4-138">c5e2524a-ea46-4f67-841f-6a9465d9d515_cw5n1h2txyewy</span><span class="sxs-lookup"><span data-stu-id="539a4-138">c5e2524a-ea46-4f67-841f-6a9465d9d515_cw5n1h2txyewy</span></span> |
| <span data-ttu-id="539a4-139">Mail</span><span class="sxs-lookup"><span data-stu-id="539a4-139">Mail</span></span>                       | <span data-ttu-id="539a4-140">microsoft.windowscommunicationsapps_8wekyb3d8bbwe</span><span class="sxs-lookup"><span data-stu-id="539a4-140">microsoft.windowscommunicationsapps_8wekyb3d8bbwe</span></span>  |
| <span data-ttu-id="539a4-141">Microsoft Store</span><span class="sxs-lookup"><span data-stu-id="539a4-141">Microsoft Store</span></span>            | <span data-ttu-id="539a4-142">Microsoft.WindowsStore_8wekyb3d8bbwe</span><span class="sxs-lookup"><span data-stu-id="539a4-142">Microsoft.WindowsStore_8wekyb3d8bbwe</span></span>               |
| <span data-ttu-id="539a4-143">Filme & TV</span><span class="sxs-lookup"><span data-stu-id="539a4-143">Movies & TV</span></span>                | <span data-ttu-id="539a4-144">Microsoft.ZuneVideo_8wekyb3d8bbwe</span><span class="sxs-lookup"><span data-stu-id="539a4-144">Microsoft.ZuneVideo_8wekyb3d8bbwe</span></span>                  |
| <span data-ttu-id="539a4-145">OneDrive</span><span class="sxs-lookup"><span data-stu-id="539a4-145">OneDrive</span></span>                   | <span data-ttu-id="539a4-146">microsoft.microsoftskydrive_8wekyb3d8bbwe</span><span class="sxs-lookup"><span data-stu-id="539a4-146">microsoft.microsoftskydrive_8wekyb3d8bbwe</span></span>          |
| <span data-ttu-id="539a4-147">Fotos</span><span class="sxs-lookup"><span data-stu-id="539a4-147">Photos</span></span>                     | <span data-ttu-id="539a4-148">Microsoft.Windows.Fotos_8wekyb3d8bbwe</span><span class="sxs-lookup"><span data-stu-id="539a4-148">Microsoft.Windows.Photos_8wekyb3d8bbwe</span></span>             |
| <span data-ttu-id="539a4-149">Einstellungen</span><span class="sxs-lookup"><span data-stu-id="539a4-149">Settings</span></span>                   | <span data-ttu-id="539a4-150">HolographicSystemSettings_cw5n1h2txyewy</span><span class="sxs-lookup"><span data-stu-id="539a4-150">HolographicSystemSettings_cw5n1h2txyewy</span></span>            |
| <span data-ttu-id="539a4-151">Tipps</span><span class="sxs-lookup"><span data-stu-id="539a4-151">Tips</span></span>                       | <span data-ttu-id="539a4-152">Microsoft.HoloLensTips_8wekyb3d8bbwe</span><span class="sxs-lookup"><span data-stu-id="539a4-152">Microsoft.HoloLensTips_8wekyb3d8bbwe</span></span>               |

- <span data-ttu-id="539a4-153">1 – Durch das Blockieren des App-Installers wird nur die App-Installer-App blockiert, und keine Apps, die aus anderen Quellen wie dem Microsoft Store oder aus Ihrer MDM-Lösung installiert wurden.</span><span class="sxs-lookup"><span data-stu-id="539a4-153">1 - Blocking App Installer will only block the App Installer app, and not apps installed from other sources such as the Microsoft Store or from your MDM solution.</span></span>

### <span data-ttu-id="539a4-154">So finden Sie einen Paketfamiliennamen</span><span class="sxs-lookup"><span data-stu-id="539a4-154">How to find a Package Family Name</span></span>

<span data-ttu-id="539a4-155">Wenn eine App nicht in dieser Liste enthalten ist, kann ein Benutzer das Geräteportal verwenden, das mit einer HoloLens 2 verbunden ist, die die App installiert hat, die blockiert werden soll, um die PackageRelativeID zu ermitteln und von dort den PackageFamilyName zu erhalten.</span><span class="sxs-lookup"><span data-stu-id="539a4-155">If an app is not on this list, then a user may use Device Portal, connected to a HoloLens 2 that has installed the app wished to be blocked, to determine the PackageRelativeID and from there get the PackageFamilyName.</span></span>

1. <span data-ttu-id="539a4-156">Installieren Sie die App auf Ihrem HoloLens 2-Gerät.</span><span class="sxs-lookup"><span data-stu-id="539a4-156">Install the app on your HoloLens 2 device.</span></span> 
1. <span data-ttu-id="539a4-157">Öffnen Sie "Einstellungen -> Updates & Sicherheit -> Für Entwickler, \*\*\*\* aktivieren Sie den Entwicklermodus und dann **das Geräteportal.**</span><span class="sxs-lookup"><span data-stu-id="539a4-157">Open Settings -> Updates & Security -> For developers, and enable **Developer mode** and then **Device portal**.</span></span> 
    1. <span data-ttu-id="539a4-158">Weitere Informationen zur Einrichtung und Verwendung des Geräteportals finden Sie [hier.](https://docs.microsoft.com/windows/mixed-reality/develop/platform-capabilities-and-apis/using-the-windows-device-portal)</span><span class="sxs-lookup"><span data-stu-id="539a4-158">More more details instructions read more about [setup and use of device portal here](https://docs.microsoft.com/windows/mixed-reality/develop/platform-capabilities-and-apis/using-the-windows-device-portal).</span></span>
1. <span data-ttu-id="539a4-159">Sobald das Geräteportal verbunden ist, navigieren Sie zu **"Ansichten"** und dann zu **"Apps".**</span><span class="sxs-lookup"><span data-stu-id="539a4-159">Once Device Portal is connected, navigate to **Views** then **Apps**.</span></span> 
1. <span data-ttu-id="539a4-160">Wählen Sie im Bereich "Installierte Apps" in der Dropdownliste die installierte App aus.</span><span class="sxs-lookup"><span data-stu-id="539a4-160">Within the Installed Apps panel, use the dropdown to select the installed app.</span></span> 
1. <span data-ttu-id="539a4-161">Suchen Sie die PackageRelativeID.</span><span class="sxs-lookup"><span data-stu-id="539a4-161">Locate the PackageRelativeID.</span></span> 
1. <span data-ttu-id="539a4-162">Kopieren Sie die Zeichen der App vor !, diese Zeichen sind Ihr PackageFamilyName.</span><span class="sxs-lookup"><span data-stu-id="539a4-162">Copy app characters before the !, these characters will be your PackageFamilyName.</span></span>


