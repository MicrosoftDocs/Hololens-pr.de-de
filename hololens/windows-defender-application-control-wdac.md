---
title: Windows Defender-Anwendungssteuerung – WDAC
description: Übersicht über die WDAC und die Verwendung zum Verwalten von HoloLens-Geräten.
ms.prod: hololens
ms.sitesec: library
author: evmill
ms.author: v-evmill
ms.topic: article
ms.localizationpriority: medium
ms.date: 09/16/2020
ms.reviewer: ''
manager: yannisle
appliesto:
- HoloLens 2
ms.openlocfilehash: d1147b202d3b575fa1f2dd20f620005c786ea9fc
ms.sourcegitcommit: 785ac6f05aecffc0f3980960891617d161711a70
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 09/17/2020
ms.locfileid: "11016778"
---
# <span data-ttu-id="94488-103">Windows Defender-Anwendungssteuerung – WDAC</span><span class="sxs-lookup"><span data-stu-id="94488-103">Windows Defender Application Control - WDAC</span></span>

<span data-ttu-id="94488-104">WDAC ermöglicht es einem IT-Administrator, seine Geräte so zu konfigurieren, dass die Einführung von apps auf Geräten blockiert wird.</span><span class="sxs-lookup"><span data-stu-id="94488-104">WDAC allows an IT Admin to configure their devices to block the launch of apps on devices.</span></span> <span data-ttu-id="94488-105">Dies unterscheidet sich von den Methoden der Geräte Einschränkung wie dem Kiosk Modus, bei dem dem Benutzer eine Benutzeroberfläche angezeigt wird, auf der die apps auf dem Gerät verborgen sind, die jedoch weiterhin gestartet werden können.</span><span class="sxs-lookup"><span data-stu-id="94488-105">This is different than methods of device restriction such as Kiosk mode, where  the user is presented with a UI that hides the apps on the device but they can still be launched.</span></span> <span data-ttu-id="94488-106">Während WDAC implementiert ist, sind die apps weiterhin in der Liste alle apps sichtbar, aber WDAC verhindert, dass diese apps und Prozesse vom Geräte Benutzer gestartet werden können.</span><span class="sxs-lookup"><span data-stu-id="94488-106">While WDAC is implemented, the apps are still visible in the All Apps list but WDAC stops those apps and processes from being able to be launched by the device user.</span></span>

> [!NOTE]
> <span data-ttu-id="94488-107">Wenn Endbenutzer versuchen, eine APP zu starten, die von WDAC blockiert wird, erhalten Sie auf HoloLens keine Benachrichtigung darüber, dass Sie die APP nicht starten können.</span><span class="sxs-lookup"><span data-stu-id="94488-107">When end users attempt to launch an app that is blocked by WDAC, on HoloLens they will not receive a notification about not being able to launch that app.</span></span>

<span data-ttu-id="94488-108">Im folgenden finden Sie eine Anleitung für Benutzer, die erfahren möchten, wie Sie [mithilfe von WDAC und Windows PowerShell apps auf HoloLens 2-Geräten mit Microsoft InTune zulassen oder blockieren](https://docs.microsoft.com/mem/intune/configuration/custom-profile-hololens).</span><span class="sxs-lookup"><span data-stu-id="94488-108">The following is a guide for users to learn how to [use WDAC and Windows PowerShell to allow or block apps on HoloLens 2 devices with Microsoft Intune](https://docs.microsoft.com/mem/intune/configuration/custom-profile-hololens).</span></span>

<span data-ttu-id="94488-109">Wenn Benutzer nach Apps suchen, die auf Ihrem Windows 10-PC mit dem ersten Beispiel Schritt installiert sind, müssen Sie möglicherweise einige Versuche Unternehmen, die Ergebnisse einzuschränken.</span><span class="sxs-lookup"><span data-stu-id="94488-109">When users search for apps installed on their Windows 10 PC using the first example step they may need to make a few attempts to narrow down the results.</span></span>

```powershell
$package1 = Get-AppxPackage -name *<applicationname>*
``` 

<span data-ttu-id="94488-110">Wenn Sie den vollständigen Namen des Pakets nicht kennen, müssen Sie möglicherweise ein paar Mal "Get-AppxPackage-Name \ \* YourBestGuess \ \*" ausführen, um es zu finden.</span><span class="sxs-lookup"><span data-stu-id="94488-110">If you don’t know the full name of the package, you may need to run ‘Get-AppxPackage -name \*YourBestGuess\*’ a few times to find it.</span></span> <span data-ttu-id="94488-111">Nachdem Sie den Namen ausgeführt haben, führen Sie "$Package 1 = Get-AppxPackage-Name ist. Paketname" aus.</span><span class="sxs-lookup"><span data-stu-id="94488-111">Then once you have the name run ‘$package1 = Get-AppxPackage -name Actual.PackageName‘</span></span>

<span data-ttu-id="94488-112">Wenn Sie beispielsweise Folgendes für Edge ausführen, wird mehr als ein Ergebnis zurückgegeben, doch aus dieser Liste können Sie erkennen, dass der vollständige Name Microsoft. MicrosoftEdge ist.</span><span class="sxs-lookup"><span data-stu-id="94488-112">For example running the following for Edge will return more than one result, but from that list you can identify that the full name you need is Microsoft.MicrosoftEdge.</span></span> 

```powershell
Get-AppxPackage -name *edge*
``` 

## <span data-ttu-id="94488-113">Paket Familiennamen für apps auf HoloLens</span><span class="sxs-lookup"><span data-stu-id="94488-113">Package Family Names for apps on HoloLens</span></span>

<span data-ttu-id="94488-114">Im obigen Leitfaden können Sie newPolicy.xml manuell bearbeiten und Regeln für Anwendungen hinzufügen, die nur auf HoloLens mit ihren Paket Familiennamen installiert sind.</span><span class="sxs-lookup"><span data-stu-id="94488-114">In the guide linked above, you can manually edit newPolicy.xml and add rules for applications which are only installed on HoloLens with their package family names.</span></span> <span data-ttu-id="94488-115">Manchmal gibt es apps, die Sie verwenden können, die nicht auf dem Desktop-PC vorhanden sind, den Sie der Richtlinie hinzufügen möchten.</span><span class="sxs-lookup"><span data-stu-id="94488-115">Sometimes there are apps you may use to use that are not on your desktop PC that you wish to add to policy.</span></span> 

<span data-ttu-id="94488-116">Nachfolgend finden Sie eine Liste der häufig verwendeten und in-Box-Apps für HoloLens 2-Geräte.</span><span class="sxs-lookup"><span data-stu-id="94488-116">Here is a list of commonly used and In-Box apps for HoloLens 2 devices.</span></span>

| <span data-ttu-id="94488-117">App-Name</span><span class="sxs-lookup"><span data-stu-id="94488-117">App Name</span></span>                   | <span data-ttu-id="94488-118">Paket Familien Name</span><span class="sxs-lookup"><span data-stu-id="94488-118">Package Family Name</span></span>                                |
|----------------------------|----------------------------------------------------|
| <span data-ttu-id="94488-119">3D-Viewer</span><span class="sxs-lookup"><span data-stu-id="94488-119">3D Viewer</span></span>                  | <span data-ttu-id="94488-120">Microsoft. Microsoft3DViewer_8wekyb3d8bbwe</span><span class="sxs-lookup"><span data-stu-id="94488-120">Microsoft.Microsoft3DViewer_8wekyb3d8bbwe</span></span>          |
| <span data-ttu-id="94488-121">Calendar</span><span class="sxs-lookup"><span data-stu-id="94488-121">Calendar</span></span>                   | <span data-ttu-id="94488-122">Microsoft. windowscommunicationsapps_8wekyb3d8bbwe</span><span class="sxs-lookup"><span data-stu-id="94488-122">microsoft.windowscommunicationsapps_8wekyb3d8bbwe</span></span>  |
| <span data-ttu-id="94488-123">Kamera</span><span class="sxs-lookup"><span data-stu-id="94488-123">Camera</span></span>                     | <span data-ttu-id="94488-124">HoloCamera_cw5n1h2txyewy</span><span class="sxs-lookup"><span data-stu-id="94488-124">HoloCamera_cw5n1h2txyewy</span></span>                           |
| <span data-ttu-id="94488-125">Cortana</span><span class="sxs-lookup"><span data-stu-id="94488-125">Cortana</span></span>                    | <span data-ttu-id="94488-126">Microsoft. 549981C3F5F10_8wekyb3d8bbwe</span><span class="sxs-lookup"><span data-stu-id="94488-126">Microsoft.549981C3F5F10_8wekyb3d8bbwe</span></span>              |
| <span data-ttu-id="94488-127">Dynamics 365 Guides</span><span class="sxs-lookup"><span data-stu-id="94488-127">Dynamics 365 Guides</span></span>        | <span data-ttu-id="94488-128">Microsoft. Dynamics365. Guides_8wekyb3d8bbwe</span><span class="sxs-lookup"><span data-stu-id="94488-128">Microsoft.Dynamics365.Guides_8wekyb3d8bbwe</span></span>         |
| <span data-ttu-id="94488-129">Dynamics 365 Remote Assist</span><span class="sxs-lookup"><span data-stu-id="94488-129">Dynamics 365 Remote Assist</span></span> | <span data-ttu-id="94488-130">Microsoft. MicrosoftRemoteAssist_8wekyb3d8bbwe</span><span class="sxs-lookup"><span data-stu-id="94488-130">Microsoft.MicrosoftRemoteAssist_8wekyb3d8bbwe</span></span>      |
| <span data-ttu-id="94488-131">Feedback-Hub</span><span class="sxs-lookup"><span data-stu-id="94488-131">Feedback Hub</span></span>               | <span data-ttu-id="94488-132">Microsoft. WindowsFeedbackHub_8wekyb3d8bbwe</span><span class="sxs-lookup"><span data-stu-id="94488-132">Microsoft.WindowsFeedbackHub_8wekyb3d8bbwe</span></span>         |
| <span data-ttu-id="94488-133">Datei-Explorer</span><span class="sxs-lookup"><span data-stu-id="94488-133">File Explorer</span></span>              | <span data-ttu-id="94488-134">c5e2524a-ea46-4f67-841f-6a9465d9d515_cw5n1h2txyewy</span><span class="sxs-lookup"><span data-stu-id="94488-134">c5e2524a-ea46-4f67-841f-6a9465d9d515_cw5n1h2txyewy</span></span> |
| <span data-ttu-id="94488-135">Mail</span><span class="sxs-lookup"><span data-stu-id="94488-135">Mail</span></span>                       | <span data-ttu-id="94488-136">Microsoft. windowscommunicationsapps_8wekyb3d8bbwe</span><span class="sxs-lookup"><span data-stu-id="94488-136">microsoft.windowscommunicationsapps_8wekyb3d8bbwe</span></span>  |
| <span data-ttu-id="94488-137">Microsoft Store</span><span class="sxs-lookup"><span data-stu-id="94488-137">Microsoft Store</span></span>            | <span data-ttu-id="94488-138">Microsoft. WindowsStore_8wekyb3d8bbwe</span><span class="sxs-lookup"><span data-stu-id="94488-138">Microsoft.WindowsStore_8wekyb3d8bbwe</span></span>               |
| <span data-ttu-id="94488-139">Filme & TV</span><span class="sxs-lookup"><span data-stu-id="94488-139">Movies & TV</span></span>                | <span data-ttu-id="94488-140">Microsoft. ZuneVideo_8wekyb3d8bbwe</span><span class="sxs-lookup"><span data-stu-id="94488-140">Microsoft.ZuneVideo_8wekyb3d8bbwe</span></span>                  |
| <span data-ttu-id="94488-141">OneDrive</span><span class="sxs-lookup"><span data-stu-id="94488-141">OneDrive</span></span>                   | <span data-ttu-id="94488-142">Microsoft. microsoftskydrive_8wekyb3d8bbwe</span><span class="sxs-lookup"><span data-stu-id="94488-142">microsoft.microsoftskydrive_8wekyb3d8bbwe</span></span>          |
| <span data-ttu-id="94488-143">Fotos</span><span class="sxs-lookup"><span data-stu-id="94488-143">Photos</span></span>                     | <span data-ttu-id="94488-144">Microsoft. Windows. Photos_8wekyb3d8bbwe</span><span class="sxs-lookup"><span data-stu-id="94488-144">Microsoft.Windows.Photos_8wekyb3d8bbwe</span></span>             |
| <span data-ttu-id="94488-145">Einstellungen</span><span class="sxs-lookup"><span data-stu-id="94488-145">Settings</span></span>                   | <span data-ttu-id="94488-146">HolographicSystemSettings_cw5n1h2txyewy</span><span class="sxs-lookup"><span data-stu-id="94488-146">HolographicSystemSettings_cw5n1h2txyewy</span></span>            |
| <span data-ttu-id="94488-147">Tipps</span><span class="sxs-lookup"><span data-stu-id="94488-147">Tips</span></span>                       | <span data-ttu-id="94488-148">Microsoft. HoloLensTips_8wekyb3d8bbwe</span><span class="sxs-lookup"><span data-stu-id="94488-148">Microsoft.HoloLensTips_8wekyb3d8bbwe</span></span>               |

<span data-ttu-id="94488-149">Wenn eine APP nicht in dieser Liste enthalten ist, kann ein Benutzer Device Portal verwenden, das mit einem HoloLens 2 verbunden ist, das die APP, die blockiert werden soll, installiert hat, um die PackageRelativeID zu ermitteln, und dann den PackageFamilyName.</span><span class="sxs-lookup"><span data-stu-id="94488-149">If an app is not on this list then a user may use Device Portal, connected to a HoloLens 2 that has installed the app wished to be blocked, to determine the PackageRelativeID and from there get the PackageFamilyName.</span></span>

1. <span data-ttu-id="94488-150">Installieren Sie die APP auf Ihrem HoloLens 2-Gerät.</span><span class="sxs-lookup"><span data-stu-id="94488-150">Install the app on your HoloLens 2 device.</span></span> 
1. <span data-ttu-id="94488-151">Öffnen Sie Einstellungen – > Updates & Securtiy-> für Entwickler, und aktivieren Sie den **Entwicklermodus** und dann **Device Portal**.</span><span class="sxs-lookup"><span data-stu-id="94488-151">Open Settings -> Updates & Securtiy -> For developers, and enable **Developer mode** and then **Device portal**.</span></span> 
    1. <span data-ttu-id="94488-152">Weitere Informationen hierzu finden Sie hier unter Weitere Informationen zum [Einrichten und Verwenden des Device Portals](https://docs.microsoft.com/windows/mixed-reality/develop/platform-capabilities-and-apis/using-the-windows-device-portal).</span><span class="sxs-lookup"><span data-stu-id="94488-152">More more details instructions read more about [setup and use of device portal here](https://docs.microsoft.com/windows/mixed-reality/develop/platform-capabilities-and-apis/using-the-windows-device-portal).</span></span>
1. <span data-ttu-id="94488-153">Wenn Device Portal verbunden ist, navigieren Sie zu **Ansichten** und dann zu **apps**.</span><span class="sxs-lookup"><span data-stu-id="94488-153">Once Device Portal is connected, navigate to **Views** then **Apps**.</span></span> 
1. <span data-ttu-id="94488-154">Verwenden Sie im Bereich installierte Apps die Dropdownliste, um die installierte App auszuwählen.</span><span class="sxs-lookup"><span data-stu-id="94488-154">Within the Installed Apps panel use the dropdown to select the installed app.</span></span> 
1. <span data-ttu-id="94488-155">Suchen Sie nach dem PackageRelativeID.</span><span class="sxs-lookup"><span data-stu-id="94488-155">Locate the PackageRelativeID.</span></span> 
1. <span data-ttu-id="94488-156">Kopieren Sie App-Zeichen vor dem!, dies ist Ihr PackageFamilyName.</span><span class="sxs-lookup"><span data-stu-id="94488-156">Copy app characters before the !, this will be your PackageFamilyName.</span></span>

