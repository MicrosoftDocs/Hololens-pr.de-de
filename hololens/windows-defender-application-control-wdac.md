---
title: Windows Defender Anwendungssteuerung – WDAC
description: Übersicht darüber, was Windows Defender Anwendungssteuerung ist und wie sie zum Verwalten von HoloLens Mixed Reality-Geräten verwendet wird.
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
ms.sourcegitcommit: ad53ba5edd567a18f0c172578d78db3190701650
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/19/2021
ms.locfileid: "108308730"
---
# <a name="windows-defender-application-control---wdac"></a><span data-ttu-id="fb3de-103">Windows Defender Anwendungssteuerung – WDAC</span><span class="sxs-lookup"><span data-stu-id="fb3de-103">Windows Defender Application Control - WDAC</span></span>

<span data-ttu-id="fb3de-104">Mit WDAC kann ein IT-Administrator seine Geräte so konfigurieren, dass der Start von Apps auf Geräten blockiert wird.</span><span class="sxs-lookup"><span data-stu-id="fb3de-104">WDAC allows an IT Admin to configure their devices to block the launch of apps on devices.</span></span> <span data-ttu-id="fb3de-105">Dies unterscheidet sich von Methoden der Geräteeinschränkung wie dem Kioskmodus, in dem dem Benutzer eine Benutzeroberfläche angezeigt wird, die die Apps auf dem Gerät ausblendet, aber trotzdem gestartet werden kann.</span><span class="sxs-lookup"><span data-stu-id="fb3de-105">This is different than methods of device restriction such as Kiosk mode, where  the user is presented with a UI that hides the apps on the device but they can still be launched.</span></span> <span data-ttu-id="fb3de-106">Während WDAC implementiert ist, sind die Apps weiterhin in der Liste Alle Apps sichtbar, aber WDAC verhindert, dass diese Apps und Prozesse vom Gerätebenutzer gestartet werden können.</span><span class="sxs-lookup"><span data-stu-id="fb3de-106">While WDAC is implemented, the apps are still visible in the All Apps list but WDAC stops those apps and processes from being able to be launched by the device user.</span></span>

<span data-ttu-id="fb3de-107">Einem Gerät können mehrere WDAC-Richtlinien zugewiesen werden.</span><span class="sxs-lookup"><span data-stu-id="fb3de-107">A device may be assigned more than one WDAC policy.</span></span> <span data-ttu-id="fb3de-108">Wenn mehrere WDAC-Richtlinien auf einem System festgelegt sind, werden die restriktivsten Richtlinien wirksam.</span><span class="sxs-lookup"><span data-stu-id="fb3de-108">If multiple WDAC policies are set on a system, most restrictive ones take effect.</span></span> 

> [!NOTE]
> <span data-ttu-id="fb3de-109">Wenn Endbenutzer versuchen, eine Von WDAC blockierte App zu starten, erhalten sie auf HoloLens keine Benachrichtigung, dass sie diese App nicht starten können.</span><span class="sxs-lookup"><span data-stu-id="fb3de-109">When end users attempt to launch an app that is blocked by WDAC, on HoloLens they will not receive a notification about not being able to launch that app.</span></span>

<span data-ttu-id="fb3de-110">Im Folgenden erfahren Benutzer, wie Sie [WDAC und Windows PowerShell verwenden, um Apps auf HoloLens 2 Geräten mit Microsoft Intune zuzulassen oder zu blockieren.](https://docs.microsoft.com/mem/intune/configuration/custom-profile-hololens)</span><span class="sxs-lookup"><span data-stu-id="fb3de-110">The following is a guide for users to learn how to [use WDAC and Windows PowerShell to allow or block apps on HoloLens 2 devices with Microsoft Intune](https://docs.microsoft.com/mem/intune/configuration/custom-profile-hololens).</span></span>

<span data-ttu-id="fb3de-111">Wenn Benutzer mit dem ersten Beispielschritt nach Apps suchen, die auf ihrem Windows 10 PC installiert sind, müssen sie möglicherweise einige Versuche unternehmen, um die Ergebnisse einzugrenzen.</span><span class="sxs-lookup"><span data-stu-id="fb3de-111">When users search for apps installed on their Windows 10 PC using the first example step, they may need to make a few attempts to narrow down the results.</span></span>

```powershell
$package1 = Get-AppxPackage -name *<applicationname>*
``` 

<span data-ttu-id="fb3de-112">Wenn Sie den vollständigen Namen des Pakets nicht kennen, müssen Sie möglicherweise mehrmals "Get-AppxPackage -name \* YourBestGuess" \* ausführen, um es zu finden.</span><span class="sxs-lookup"><span data-stu-id="fb3de-112">If you don’t know the full name of the package, you may need to run ‘Get-AppxPackage -name \*YourBestGuess\*’ a few times to find it.</span></span> <span data-ttu-id="fb3de-113">Sobald Sie den Namen haben, führen Sie "$package 1 = Get-AppxPackage -name Actual.PackageName" aus.</span><span class="sxs-lookup"><span data-stu-id="fb3de-113">Then once you have the name run ‘$package1 = Get-AppxPackage -name Actual.PackageName‘</span></span>

<span data-ttu-id="fb3de-114">Wenn Sie z. B. folgendes für Microsoft Edge ausführen, geben Sie mehr als ein Ergebnis zurück. Aus dieser Liste können Sie jedoch erkennen, dass der vollständige Name, den Sie benötigen, Microsoft.MicrosoftEdge lautet.</span><span class="sxs-lookup"><span data-stu-id="fb3de-114">For example running the following for Microsoft Edge will return more than one result, but from that list you can identify that the full name you need is Microsoft.MicrosoftEdge.</span></span>

```powershell
Get-AppxPackage -name *edge*
``` 

## <a name="package-family-names-for-apps-on-hololens"></a><span data-ttu-id="fb3de-115">Paketfamiliennamen für Apps auf HoloLens</span><span class="sxs-lookup"><span data-stu-id="fb3de-115">Package Family Names for apps on HoloLens</span></span>

<span data-ttu-id="fb3de-116">In der oben verlinkten Anleitung können Sie newPolicy.xml manuell bearbeiten und Regeln für Anwendungen hinzufügen, die nur auf HoloLens mit ihren Paketfamiliennamen installiert sind.</span><span class="sxs-lookup"><span data-stu-id="fb3de-116">In the guide linked above, you can manually edit newPolicy.xml and add rules for applications that are only installed on HoloLens with their package family names.</span></span> <span data-ttu-id="fb3de-117">Manchmal gibt es Apps, die Sie verwenden können, die sich nicht auf Ihrem Desktop-PC befinden, die Sie der Richtlinie hinzufügen möchten.</span><span class="sxs-lookup"><span data-stu-id="fb3de-117">Sometimes there are apps you may use to use that are not on your desktop PC that you wish to add to policy.</span></span>

<span data-ttu-id="fb3de-118">Hier finden Sie eine Liste der häufig verwendeten und In-Box Apps für HoloLens 2 Geräte.</span><span class="sxs-lookup"><span data-stu-id="fb3de-118">Here is a list of commonly used and In-Box apps for HoloLens 2 devices.</span></span>

| <span data-ttu-id="fb3de-119">App-Name</span><span class="sxs-lookup"><span data-stu-id="fb3de-119">App Name</span></span>                   | <span data-ttu-id="fb3de-120">Paketfamilienname</span><span class="sxs-lookup"><span data-stu-id="fb3de-120">Package Family Name</span></span>                                |
|----------------------------|----------------------------------------------------|
| <span data-ttu-id="fb3de-121">3D-Viewer</span><span class="sxs-lookup"><span data-stu-id="fb3de-121">3D Viewer</span></span>                  | <span data-ttu-id="fb3de-122">Microsoft.Microsoft3DViewer_8wekyb3d8bbwe</span><span class="sxs-lookup"><span data-stu-id="fb3de-122">Microsoft.Microsoft3DViewer_8wekyb3d8bbwe</span></span>          |
| <span data-ttu-id="fb3de-123">App-Installer</span><span class="sxs-lookup"><span data-stu-id="fb3de-123">App Installer</span></span>              | <span data-ttu-id="fb3de-124">Microsoft.DesktopAppInstaller_8wekyb3d8bbwe <sup>1</sup></span><span class="sxs-lookup"><span data-stu-id="fb3de-124">Microsoft.DesktopAppInstaller_8wekyb3d8bbwe <sup>1</sup></span></span>         |
| <span data-ttu-id="fb3de-125">Kalender</span><span class="sxs-lookup"><span data-stu-id="fb3de-125">Calendar</span></span>                   | <span data-ttu-id="fb3de-126">microsoft.windowscommunicationsapps_8wekyb3d8bbwe</span><span class="sxs-lookup"><span data-stu-id="fb3de-126">microsoft.windowscommunicationsapps_8wekyb3d8bbwe</span></span>  |
| <span data-ttu-id="fb3de-127">Kamera</span><span class="sxs-lookup"><span data-stu-id="fb3de-127">Camera</span></span>                     | <span data-ttu-id="fb3de-128">HoloCamera_cw5n1h2txyewy</span><span class="sxs-lookup"><span data-stu-id="fb3de-128">HoloCamera_cw5n1h2txyewy</span></span>                           |
| <span data-ttu-id="fb3de-129">Cortana</span><span class="sxs-lookup"><span data-stu-id="fb3de-129">Cortana</span></span>                    | <span data-ttu-id="fb3de-130">Microsoft.549981C3F5F10_8wekyb3d8bbwe</span><span class="sxs-lookup"><span data-stu-id="fb3de-130">Microsoft.549981C3F5F10_8wekyb3d8bbwe</span></span>              |
| <span data-ttu-id="fb3de-131">Dynamics 365-Leitfäden</span><span class="sxs-lookup"><span data-stu-id="fb3de-131">Dynamics 365 Guides</span></span>        | <span data-ttu-id="fb3de-132">Microsoft.Dynamics365.Guides_8wekyb3d8bbwe</span><span class="sxs-lookup"><span data-stu-id="fb3de-132">Microsoft.Dynamics365.Guides_8wekyb3d8bbwe</span></span>         |
| <span data-ttu-id="fb3de-133">Dynamics 365 Remote Assist</span><span class="sxs-lookup"><span data-stu-id="fb3de-133">Dynamics 365 Remote Assist</span></span> | <span data-ttu-id="fb3de-134">Microsoft.MicrosoftRemoteAssist_8wekyb3d8bbwe</span><span class="sxs-lookup"><span data-stu-id="fb3de-134">Microsoft.MicrosoftRemoteAssist_8wekyb3d8bbwe</span></span>      |
| <span data-ttu-id="fb3de-135">Feedback-Hub</span><span class="sxs-lookup"><span data-stu-id="fb3de-135">Feedback Hub</span></span>               | <span data-ttu-id="fb3de-136">Microsoft.WindowsFeedbackHub_8wekyb3d8bbwe</span><span class="sxs-lookup"><span data-stu-id="fb3de-136">Microsoft.WindowsFeedbackHub_8wekyb3d8bbwe</span></span>         |
| <span data-ttu-id="fb3de-137">Datei-Explorer</span><span class="sxs-lookup"><span data-stu-id="fb3de-137">File Explorer</span></span>              | <span data-ttu-id="fb3de-138">c5e2524a-ea46-4f67-841f-6a9465d9d515_cw5n1h2txyewy</span><span class="sxs-lookup"><span data-stu-id="fb3de-138">c5e2524a-ea46-4f67-841f-6a9465d9d515_cw5n1h2txyewy</span></span> |
| <span data-ttu-id="fb3de-139">E-Mail</span><span class="sxs-lookup"><span data-stu-id="fb3de-139">Mail</span></span>                       | <span data-ttu-id="fb3de-140">microsoft.windowscommunicationsapps_8wekyb3d8bbwe</span><span class="sxs-lookup"><span data-stu-id="fb3de-140">microsoft.windowscommunicationsapps_8wekyb3d8bbwe</span></span>  |
| <span data-ttu-id="fb3de-141">Microsoft Store</span><span class="sxs-lookup"><span data-stu-id="fb3de-141">Microsoft Store</span></span>            | <span data-ttu-id="fb3de-142">Microsoft.WindowsStore_8wekyb3d8bbwe</span><span class="sxs-lookup"><span data-stu-id="fb3de-142">Microsoft.WindowsStore_8wekyb3d8bbwe</span></span>               |
| <span data-ttu-id="fb3de-143">Filme & TV</span><span class="sxs-lookup"><span data-stu-id="fb3de-143">Movies & TV</span></span>                | <span data-ttu-id="fb3de-144">Microsoft.ZuneVideo_8wekyb3d8bbwe</span><span class="sxs-lookup"><span data-stu-id="fb3de-144">Microsoft.ZuneVideo_8wekyb3d8bbwe</span></span>                  |
| <span data-ttu-id="fb3de-145">OneDrive</span><span class="sxs-lookup"><span data-stu-id="fb3de-145">OneDrive</span></span>                   | <span data-ttu-id="fb3de-146">microsoft.microsoftskydrive_8wekyb3d8bbwe</span><span class="sxs-lookup"><span data-stu-id="fb3de-146">microsoft.microsoftskydrive_8wekyb3d8bbwe</span></span>          |
| <span data-ttu-id="fb3de-147">Fotos</span><span class="sxs-lookup"><span data-stu-id="fb3de-147">Photos</span></span>                     | <span data-ttu-id="fb3de-148">Microsoft.Windows.Photos_8wekyb3d8bbwe</span><span class="sxs-lookup"><span data-stu-id="fb3de-148">Microsoft.Windows.Photos_8wekyb3d8bbwe</span></span>             |
| <span data-ttu-id="fb3de-149">Einstellung</span><span class="sxs-lookup"><span data-stu-id="fb3de-149">Settings</span></span>                   | <span data-ttu-id="fb3de-150">HolographicSystemSettings_cw5n1h2txyewy</span><span class="sxs-lookup"><span data-stu-id="fb3de-150">HolographicSystemSettings_cw5n1h2txyewy</span></span>            |
| <span data-ttu-id="fb3de-151">Tipps</span><span class="sxs-lookup"><span data-stu-id="fb3de-151">Tips</span></span>                       | <span data-ttu-id="fb3de-152">Microsoft.HoloLensTips_8wekyb3d8bbwe</span><span class="sxs-lookup"><span data-stu-id="fb3de-152">Microsoft.HoloLensTips_8wekyb3d8bbwe</span></span>               |

- <span data-ttu-id="fb3de-153">1 – App-Installer blockieren, wird nur die App-Installer-App blockiert und keine Apps, die aus anderen Quellen wie der Microsoft Store oder aus Ihrer MDM-Lösung installiert wurden.</span><span class="sxs-lookup"><span data-stu-id="fb3de-153">1 - Blocking App Installer will only block the App Installer app, and not apps installed from other sources such as the Microsoft Store or from your MDM solution.</span></span>

### <a name="how-to-find-a-package-family-name"></a><span data-ttu-id="fb3de-154">Suchen eines Paketfamiliennamens</span><span class="sxs-lookup"><span data-stu-id="fb3de-154">How to find a Package Family Name</span></span>

<span data-ttu-id="fb3de-155">Wenn eine App nicht in dieser Liste enthalten ist, kann ein Benutzer Geräteportal verwenden, das mit einem HoloLens 2 verbunden ist, auf dem die App installiert wurde, die blockiert werden soll, um packageRelativeID zu bestimmen und von dort den PackageFamilyName zu erhalten.</span><span class="sxs-lookup"><span data-stu-id="fb3de-155">If an app is not on this list, then a user may use Device Portal, connected to a HoloLens 2 that has installed the app wished to be blocked, to determine the PackageRelativeID and from there get the PackageFamilyName.</span></span>

1. <span data-ttu-id="fb3de-156">Installieren Sie die App auf Ihrem HoloLens 2 Gerät.</span><span class="sxs-lookup"><span data-stu-id="fb3de-156">Install the app on your HoloLens 2 device.</span></span> 
1. <span data-ttu-id="fb3de-157">Öffnen Sie Einstellungen -> Updates & Sicherheit -> Für Entwickler, und aktivieren Sie den **Entwicklermodus** und dann das **Geräteportal.**</span><span class="sxs-lookup"><span data-stu-id="fb3de-157">Open Settings -> Updates & Security -> For developers, and enable **Developer mode** and then **Device portal**.</span></span> 
    1. <span data-ttu-id="fb3de-158">Ausführlichere Anweisungen zum [Einrichten und Verwenden des Geräteportals finden Sie hier.](https://docs.microsoft.com/windows/mixed-reality/develop/platform-capabilities-and-apis/using-the-windows-device-portal)</span><span class="sxs-lookup"><span data-stu-id="fb3de-158">More more details instructions read more about [setup and use of device portal here](https://docs.microsoft.com/windows/mixed-reality/develop/platform-capabilities-and-apis/using-the-windows-device-portal).</span></span>
1. <span data-ttu-id="fb3de-159">Sobald Geräteportal verbunden ist, navigieren Sie zu **Ansichten** und dann **zu Apps.**</span><span class="sxs-lookup"><span data-stu-id="fb3de-159">Once Device Portal is connected, navigate to **Views** then **Apps**.</span></span> 
1. <span data-ttu-id="fb3de-160">Wählen Sie im Bereich Installierte Apps die Dropdownliste aus, um die installierte App auszuwählen.</span><span class="sxs-lookup"><span data-stu-id="fb3de-160">Within the Installed Apps panel, use the dropdown to select the installed app.</span></span> 
1. <span data-ttu-id="fb3de-161">Suchen Sie nach PackageRelativeID.</span><span class="sxs-lookup"><span data-stu-id="fb3de-161">Locate the PackageRelativeID.</span></span> 
1. <span data-ttu-id="fb3de-162">Kopieren Sie App-Zeichen vor !, diese Zeichen sind Ihr PackageFamilyName.</span><span class="sxs-lookup"><span data-stu-id="fb3de-162">Copy app characters before the !, these characters will be your PackageFamilyName.</span></span>


