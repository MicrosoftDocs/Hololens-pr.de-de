---
title: Windows Defender Application Control – WDAC
description: Übersicht über die WDAC und die Verwendung zum Verwalten von HoloLens-Geräten.
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
ms.openlocfilehash: b12079142049cce28ec00803ad0a1f8dc92333e1
ms.sourcegitcommit: 108b818130e2627bf08107f4e47ae159dd6ab1d2
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/10/2020
ms.locfileid: "11163119"
---
# <span data-ttu-id="93c23-103">Windows Defender Application Control – WDAC</span><span class="sxs-lookup"><span data-stu-id="93c23-103">Windows Defender Application Control - WDAC</span></span>

<span data-ttu-id="93c23-104">WDAC ermöglicht es einem IT-Administrator, seine Geräte so zu konfigurieren, dass die Einführung von apps auf Geräten blockiert wird.</span><span class="sxs-lookup"><span data-stu-id="93c23-104">WDAC allows an IT Admin to configure their devices to block the launch of apps on devices.</span></span> <span data-ttu-id="93c23-105">Dies unterscheidet sich von den Methoden der Geräte Einschränkung wie dem Kiosk Modus, bei dem dem Benutzer eine Benutzeroberfläche angezeigt wird, auf der die apps auf dem Gerät verborgen sind, die jedoch weiterhin gestartet werden können.</span><span class="sxs-lookup"><span data-stu-id="93c23-105">This is different than methods of device restriction such as Kiosk mode, where  the user is presented with a UI that hides the apps on the device but they can still be launched.</span></span> <span data-ttu-id="93c23-106">Während WDAC implementiert ist, sind die apps weiterhin in der Liste alle apps sichtbar, aber WDAC verhindert, dass diese apps und Prozesse vom Geräte Benutzer gestartet werden können.</span><span class="sxs-lookup"><span data-stu-id="93c23-106">While WDAC is implemented, the apps are still visible in the All Apps list but WDAC stops those apps and processes from being able to be launched by the device user.</span></span>

<span data-ttu-id="93c23-107">Einem Gerät kann mehr als eine WDAC-Richtlinie zugewiesen werden.</span><span class="sxs-lookup"><span data-stu-id="93c23-107">A device may be assigned more than one WDAC policy.</span></span> <span data-ttu-id="93c23-108">Wenn mehrere WDAC-Richtlinien auf einem System eingestellt sind, werden die meisten restriktiven wirksam.</span><span class="sxs-lookup"><span data-stu-id="93c23-108">If multiple WDAC policies are set on a system, most restrictive ones take effect.</span></span> 

> [!NOTE]
> <span data-ttu-id="93c23-109">Wenn Endbenutzer versuchen, eine APP zu starten, die von WDAC blockiert wird, erhalten Sie auf HoloLens keine Benachrichtigung darüber, dass Sie die APP nicht starten können.</span><span class="sxs-lookup"><span data-stu-id="93c23-109">When end users attempt to launch an app that is blocked by WDAC, on HoloLens they will not receive a notification about not being able to launch that app.</span></span>

<span data-ttu-id="93c23-110">Im folgenden finden Sie eine Anleitung für Benutzer, die erfahren möchten, wie Sie [mithilfe von WDAC und Windows PowerShell apps auf HoloLens 2-Geräten mit Microsoft InTune zulassen oder blockieren](https://docs.microsoft.com/mem/intune/configuration/custom-profile-hololens).</span><span class="sxs-lookup"><span data-stu-id="93c23-110">The following is a guide for users to learn how to [use WDAC and Windows PowerShell to allow or block apps on HoloLens 2 devices with Microsoft Intune](https://docs.microsoft.com/mem/intune/configuration/custom-profile-hololens).</span></span>

<span data-ttu-id="93c23-111">Wenn Benutzer nach Apps suchen, die auf Ihrem Windows 10-PC mit dem ersten Beispiel Schritt installiert sind, müssen Sie möglicherweise einige Versuche Unternehmen, die Ergebnisse einzuschränken.</span><span class="sxs-lookup"><span data-stu-id="93c23-111">When users search for apps installed on their Windows 10 PC using the first example step they may need to make a few attempts to narrow down the results.</span></span>

```powershell
$package1 = Get-AppxPackage -name *<applicationname>*
``` 

<span data-ttu-id="93c23-112">Wenn Sie den vollständigen Namen des Pakets nicht kennen, müssen Sie möglicherweise ein paar Mal "Get-AppxPackage-Name \ \* YourBestGuess \ \*" ausführen, um es zu finden.</span><span class="sxs-lookup"><span data-stu-id="93c23-112">If you don’t know the full name of the package, you may need to run ‘Get-AppxPackage -name \*YourBestGuess\*’ a few times to find it.</span></span> <span data-ttu-id="93c23-113">Nachdem Sie den Namen ausgeführt haben, führen Sie "$Package 1 = Get-AppxPackage-Name ist. Paketname" aus.</span><span class="sxs-lookup"><span data-stu-id="93c23-113">Then once you have the name run ‘$package1 = Get-AppxPackage -name Actual.PackageName‘</span></span>

<span data-ttu-id="93c23-114">Wenn Sie beispielsweise Folgendes für Edge ausführen, wird mehr als ein Ergebnis zurückgegeben, doch aus dieser Liste können Sie erkennen, dass der vollständige Name Microsoft. MicrosoftEdge ist.</span><span class="sxs-lookup"><span data-stu-id="93c23-114">For example running the following for Edge will return more than one result, but from that list you can identify that the full name you need is Microsoft.MicrosoftEdge.</span></span> 

```powershell
Get-AppxPackage -name *edge*
``` 

## <span data-ttu-id="93c23-115">Paket Familiennamen für apps auf HoloLens</span><span class="sxs-lookup"><span data-stu-id="93c23-115">Package Family Names for apps on HoloLens</span></span>

<span data-ttu-id="93c23-116">Im obigen Leitfaden können Sie newPolicy.xml manuell bearbeiten und Regeln für Anwendungen hinzufügen, die nur auf HoloLens mit ihren Paket Familiennamen installiert sind.</span><span class="sxs-lookup"><span data-stu-id="93c23-116">In the guide linked above, you can manually edit newPolicy.xml and add rules for applications which are only installed on HoloLens with their package family names.</span></span> <span data-ttu-id="93c23-117">Manchmal gibt es apps, die Sie verwenden können, die nicht auf dem Desktop-PC vorhanden sind, den Sie der Richtlinie hinzufügen möchten.</span><span class="sxs-lookup"><span data-stu-id="93c23-117">Sometimes there are apps you may use to use that are not on your desktop PC that you wish to add to policy.</span></span> 

<span data-ttu-id="93c23-118">Nachfolgend finden Sie eine Liste der häufig verwendeten und In-Box-Apps für HoloLens 2-Geräte.</span><span class="sxs-lookup"><span data-stu-id="93c23-118">Here is a list of commonly used and In-Box apps for HoloLens 2 devices.</span></span>

| <span data-ttu-id="93c23-119">App-Name</span><span class="sxs-lookup"><span data-stu-id="93c23-119">App Name</span></span>                   | <span data-ttu-id="93c23-120">Paket Familien Name</span><span class="sxs-lookup"><span data-stu-id="93c23-120">Package Family Name</span></span>                                |
|----------------------------|----------------------------------------------------|
| <span data-ttu-id="93c23-121">3D-Viewer</span><span class="sxs-lookup"><span data-stu-id="93c23-121">3D Viewer</span></span>                  | <span data-ttu-id="93c23-122">Microsoft.Microsoft3DViewer_8wekyb3d8bbwe</span><span class="sxs-lookup"><span data-stu-id="93c23-122">Microsoft.Microsoft3DViewer_8wekyb3d8bbwe</span></span>          |
| <span data-ttu-id="93c23-123">App-Installer</span><span class="sxs-lookup"><span data-stu-id="93c23-123">App Installer</span></span>              | <span data-ttu-id="93c23-124">Microsoft.DesktopAppInstaller_8wekyb3d8bbwe <sup> 1</span><span class="sxs-lookup"><span data-stu-id="93c23-124">Microsoft.DesktopAppInstaller_8wekyb3d8bbwe <sup>1</span></span></sup>         |
| <span data-ttu-id="93c23-125">Calendar</span><span class="sxs-lookup"><span data-stu-id="93c23-125">Calendar</span></span>                   | <span data-ttu-id="93c23-126">microsoft.windowscommunicationsapps_8wekyb3d8bbwe</span><span class="sxs-lookup"><span data-stu-id="93c23-126">microsoft.windowscommunicationsapps_8wekyb3d8bbwe</span></span>  |
| <span data-ttu-id="93c23-127">Kamera</span><span class="sxs-lookup"><span data-stu-id="93c23-127">Camera</span></span>                     | <span data-ttu-id="93c23-128">HoloCamera_cw5n1h2txyewy</span><span class="sxs-lookup"><span data-stu-id="93c23-128">HoloCamera_cw5n1h2txyewy</span></span>                           |
| <span data-ttu-id="93c23-129">Cortana</span><span class="sxs-lookup"><span data-stu-id="93c23-129">Cortana</span></span>                    | <span data-ttu-id="93c23-130">Microsoft.549981C3F5F10_8wekyb3d8bbwe</span><span class="sxs-lookup"><span data-stu-id="93c23-130">Microsoft.549981C3F5F10_8wekyb3d8bbwe</span></span>              |
| <span data-ttu-id="93c23-131">Dynamics 365 Guides</span><span class="sxs-lookup"><span data-stu-id="93c23-131">Dynamics 365 Guides</span></span>        | <span data-ttu-id="93c23-132">Microsoft.Dynamics365.Guides_8wekyb3d8bbwe</span><span class="sxs-lookup"><span data-stu-id="93c23-132">Microsoft.Dynamics365.Guides_8wekyb3d8bbwe</span></span>         |
| <span data-ttu-id="93c23-133">Dynamics 365 Remote Assist</span><span class="sxs-lookup"><span data-stu-id="93c23-133">Dynamics 365 Remote Assist</span></span> | <span data-ttu-id="93c23-134">Microsoft.MicrosoftRemoteAssist_8wekyb3d8bbwe</span><span class="sxs-lookup"><span data-stu-id="93c23-134">Microsoft.MicrosoftRemoteAssist_8wekyb3d8bbwe</span></span>      |
| <span data-ttu-id="93c23-135">Feedback-Hub</span><span class="sxs-lookup"><span data-stu-id="93c23-135">Feedback Hub</span></span>               | <span data-ttu-id="93c23-136">Microsoft.WindowsFeedbackHub_8wekyb3d8bbwe</span><span class="sxs-lookup"><span data-stu-id="93c23-136">Microsoft.WindowsFeedbackHub_8wekyb3d8bbwe</span></span>         |
| <span data-ttu-id="93c23-137">Datei-Explorer</span><span class="sxs-lookup"><span data-stu-id="93c23-137">File Explorer</span></span>              | <span data-ttu-id="93c23-138">c5e2524a-ea46-4f67-841f-6a9465d9d515_cw5n1h2txyewy</span><span class="sxs-lookup"><span data-stu-id="93c23-138">c5e2524a-ea46-4f67-841f-6a9465d9d515_cw5n1h2txyewy</span></span> |
| <span data-ttu-id="93c23-139">Mail</span><span class="sxs-lookup"><span data-stu-id="93c23-139">Mail</span></span>                       | <span data-ttu-id="93c23-140">microsoft.windowscommunicationsapps_8wekyb3d8bbwe</span><span class="sxs-lookup"><span data-stu-id="93c23-140">microsoft.windowscommunicationsapps_8wekyb3d8bbwe</span></span>  |
| <span data-ttu-id="93c23-141">Microsoft Store</span><span class="sxs-lookup"><span data-stu-id="93c23-141">Microsoft Store</span></span>            | <span data-ttu-id="93c23-142">Microsoft.WindowsStore_8wekyb3d8bbwe</span><span class="sxs-lookup"><span data-stu-id="93c23-142">Microsoft.WindowsStore_8wekyb3d8bbwe</span></span>               |
| <span data-ttu-id="93c23-143">Filme & TV</span><span class="sxs-lookup"><span data-stu-id="93c23-143">Movies & TV</span></span>                | <span data-ttu-id="93c23-144">Microsoft.ZuneVideo_8wekyb3d8bbwe</span><span class="sxs-lookup"><span data-stu-id="93c23-144">Microsoft.ZuneVideo_8wekyb3d8bbwe</span></span>                  |
| <span data-ttu-id="93c23-145">OneDrive</span><span class="sxs-lookup"><span data-stu-id="93c23-145">OneDrive</span></span>                   | <span data-ttu-id="93c23-146">microsoft.microsoftskydrive_8wekyb3d8bbwe</span><span class="sxs-lookup"><span data-stu-id="93c23-146">microsoft.microsoftskydrive_8wekyb3d8bbwe</span></span>          |
| <span data-ttu-id="93c23-147">Fotos</span><span class="sxs-lookup"><span data-stu-id="93c23-147">Photos</span></span>                     | <span data-ttu-id="93c23-148">Microsoft.Windows.Photos_8wekyb3d8bbwe</span><span class="sxs-lookup"><span data-stu-id="93c23-148">Microsoft.Windows.Photos_8wekyb3d8bbwe</span></span>             |
| <span data-ttu-id="93c23-149">Einstellungen</span><span class="sxs-lookup"><span data-stu-id="93c23-149">Settings</span></span>                   | <span data-ttu-id="93c23-150">HolographicSystemSettings_cw5n1h2txyewy</span><span class="sxs-lookup"><span data-stu-id="93c23-150">HolographicSystemSettings_cw5n1h2txyewy</span></span>            |
| <span data-ttu-id="93c23-151">Tipps</span><span class="sxs-lookup"><span data-stu-id="93c23-151">Tips</span></span>                       | <span data-ttu-id="93c23-152">Microsoft.HoloLensTips_8wekyb3d8bbwe</span><span class="sxs-lookup"><span data-stu-id="93c23-152">Microsoft.HoloLensTips_8wekyb3d8bbwe</span></span>               |

- <span data-ttu-id="93c23-153">Das 1-blockierende App-Installationsprogramm blockiert nur die APP-Installer-app und keine apps, die aus anderen Quellen wie dem Microsoft Store oder aus ihrer MDM-Lösung installiert werden.</span><span class="sxs-lookup"><span data-stu-id="93c23-153">1 - Blocking App Installer will only block the App Installer app, and not apps installed from other sources such as the Microsoft Store or from your MDM solution.</span></span>

### <span data-ttu-id="93c23-154">So suchen Sie nach einem Paket Familiennamen</span><span class="sxs-lookup"><span data-stu-id="93c23-154">How to find a Package Family Name</span></span>

<span data-ttu-id="93c23-155">Wenn eine APP nicht in dieser Liste enthalten ist, kann ein Benutzer Device Portal verwenden, das mit einem HoloLens 2 verbunden ist, das die APP, die blockiert werden soll, installiert hat, um die PackageRelativeID zu ermitteln, und dann den PackageFamilyName.</span><span class="sxs-lookup"><span data-stu-id="93c23-155">If an app is not on this list then a user may use Device Portal, connected to a HoloLens 2 that has installed the app wished to be blocked, to determine the PackageRelativeID and from there get the PackageFamilyName.</span></span>

1. <span data-ttu-id="93c23-156">Installieren Sie die APP auf Ihrem HoloLens 2-Gerät.</span><span class="sxs-lookup"><span data-stu-id="93c23-156">Install the app on your HoloLens 2 device.</span></span> 
1. <span data-ttu-id="93c23-157">Öffnen Sie Einstellungen – > Updates & Security-> für Entwickler, und aktivieren Sie den **Entwicklermodus** und dann **Device Portal**.</span><span class="sxs-lookup"><span data-stu-id="93c23-157">Open Settings -> Updates & Security -> For developers, and enable **Developer mode** and then **Device portal**.</span></span> 
    1. <span data-ttu-id="93c23-158">Weitere Informationen hierzu finden Sie hier unter Weitere Informationen zum [Einrichten und Verwenden des Device Portals](https://docs.microsoft.com/windows/mixed-reality/develop/platform-capabilities-and-apis/using-the-windows-device-portal).</span><span class="sxs-lookup"><span data-stu-id="93c23-158">More more details instructions read more about [setup and use of device portal here](https://docs.microsoft.com/windows/mixed-reality/develop/platform-capabilities-and-apis/using-the-windows-device-portal).</span></span>
1. <span data-ttu-id="93c23-159">Wenn Device Portal verbunden ist, navigieren Sie zu **Ansichten** und dann zu **apps**.</span><span class="sxs-lookup"><span data-stu-id="93c23-159">Once Device Portal is connected, navigate to **Views** then **Apps**.</span></span> 
1. <span data-ttu-id="93c23-160">Verwenden Sie im Bereich installierte Apps die Dropdownliste, um die installierte App auszuwählen.</span><span class="sxs-lookup"><span data-stu-id="93c23-160">Within the Installed Apps panel use the dropdown to select the installed app.</span></span> 
1. <span data-ttu-id="93c23-161">Suchen Sie nach dem PackageRelativeID.</span><span class="sxs-lookup"><span data-stu-id="93c23-161">Locate the PackageRelativeID.</span></span> 
1. <span data-ttu-id="93c23-162">Kopieren Sie App-Zeichen vor dem!, dies ist Ihr PackageFamilyName.</span><span class="sxs-lookup"><span data-stu-id="93c23-162">Copy app characters before the !, this will be your PackageFamilyName.</span></span>


