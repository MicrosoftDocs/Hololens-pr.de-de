---
title: Windows Defender Application Control – WDAC
description: Übersicht darüber, was Windows Defender Application Control ist und wie sie zum Verwalten HoloLens Mixed Reality-Geräten verwendet wird.
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
ms.openlocfilehash: a27a16913873c5245f734dbe084eb2b7ed007c20
ms.sourcegitcommit: 4c15afc772fba26683d9b75e38c44a018b4889f6
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 07/12/2021
ms.locfileid: "113639929"
---
# <a name="windows-defender-application-control---wdac"></a><span data-ttu-id="4b25d-103">Windows Defender Application Control – WDAC</span><span class="sxs-lookup"><span data-stu-id="4b25d-103">Windows Defender Application Control - WDAC</span></span>

<span data-ttu-id="4b25d-104">Mit WDAC kann ein IT-Administrator seine Geräte so konfigurieren, dass der Start von Apps auf Geräten blockiert wird.</span><span class="sxs-lookup"><span data-stu-id="4b25d-104">WDAC allows an IT Admin to configure their devices to block the launch of apps on devices.</span></span> <span data-ttu-id="4b25d-105">Dies unterscheidet sich von Methoden der Geräteeinschränkung wie dem Kioskmodus, in dem dem Benutzer eine Benutzeroberfläche angezeigt wird, die die Apps auf dem Gerät ausblendet, aber trotzdem gestartet werden kann.</span><span class="sxs-lookup"><span data-stu-id="4b25d-105">This is different than methods of device restriction such as Kiosk mode, where  the user is presented with a UI that hides the apps on the device but they can still be launched.</span></span> <span data-ttu-id="4b25d-106">Während WDAC implementiert ist, sind die Apps weiterhin in der Liste Alle Apps sichtbar, aber WDAC verhindert, dass diese Apps und Prozesse vom Gerätebenutzer gestartet werden können.</span><span class="sxs-lookup"><span data-stu-id="4b25d-106">While WDAC is implemented, the apps are still visible in the All Apps list but WDAC stops those apps and processes from being able to be launched by the device user.</span></span>

<span data-ttu-id="4b25d-107">Einem Gerät können mehrere WDAC-Richtlinien zugewiesen werden.</span><span class="sxs-lookup"><span data-stu-id="4b25d-107">A device may be assigned more than one WDAC policy.</span></span> <span data-ttu-id="4b25d-108">Wenn mehrere WDAC-Richtlinien auf einem System festgelegt sind, werden die restriktivsten Richtlinien wirksam.</span><span class="sxs-lookup"><span data-stu-id="4b25d-108">If multiple WDAC policies are set on a system, most restrictive ones take effect.</span></span> 

> [!NOTE]
> <span data-ttu-id="4b25d-109">Wenn Endbenutzer versuchen, eine Von WDAC blockierte App zu starten, erhalten sie auf HoloLens keine Benachrichtigung darüber, dass sie diese App nicht starten kann.</span><span class="sxs-lookup"><span data-stu-id="4b25d-109">When end users attempt to launch an app that is blocked by WDAC, on HoloLens they will not receive a notification about not being able to launch that app.</span></span>

<span data-ttu-id="4b25d-110">Im Folgenden erfahren Benutzer, wie Sie [WDAC und Windows PowerShell verwenden, um Apps auf HoloLens 2 Geräten mit Microsoft Intune zuzulassen oder zu blockieren.](/mem/intune/configuration/custom-profile-hololens)</span><span class="sxs-lookup"><span data-stu-id="4b25d-110">The following is a guide for users to learn how to [use WDAC and Windows PowerShell to allow or block apps on HoloLens 2 devices with Microsoft Intune](/mem/intune/configuration/custom-profile-hololens).</span></span>

<span data-ttu-id="4b25d-111">Wenn Benutzer im ersten Beispielschritt auf ihrem Windows 10 PC nach installierten Apps suchen, müssen sie möglicherweise einige Versuche unternehmen, um die Ergebnisse einzugrenzen.</span><span class="sxs-lookup"><span data-stu-id="4b25d-111">When users search for apps installed on their Windows 10 PC using the first example step, they may need to make a few attempts to narrow down the results.</span></span>

```powershell
$package1 = Get-AppxPackage -name *<applicationname>*
``` 

<span data-ttu-id="4b25d-112">Wenn Sie den vollständigen Namen des Pakets nicht kennen, müssen Sie möglicherweise mehrmals "Get-AppxPackage -name \* YourBestGuess" \* ausführen, um es zu finden.</span><span class="sxs-lookup"><span data-stu-id="4b25d-112">If you don’t know the full name of the package, you may need to run ‘Get-AppxPackage -name \*YourBestGuess\*’ a few times to find it.</span></span> <span data-ttu-id="4b25d-113">Sobald Sie den Namen haben, führen Sie "$package 1 = Get-AppxPackage -name Actual.PackageName" aus.</span><span class="sxs-lookup"><span data-stu-id="4b25d-113">Then once you have the name run ‘$package1 = Get-AppxPackage -name Actual.PackageName‘</span></span>

<span data-ttu-id="4b25d-114">Wenn Sie z. B. folgendes für Microsoft Edge ausführen, werden mehrere Ergebnisse zurückgegeben. Aus dieser Liste können Sie jedoch erkennen, dass der vollständige Name, den Sie benötigen, Microsoft.MicrosoftEdge lautet.</span><span class="sxs-lookup"><span data-stu-id="4b25d-114">For example running the following for Microsoft Edge will return more than one result, but from that list you can identify that the full name you need is Microsoft.MicrosoftEdge.</span></span>

```powershell
Get-AppxPackage -name *edge*
``` 

## <a name="package-family-names-for-apps-on-hololens"></a><span data-ttu-id="4b25d-115">Paketfamiliennamen für Apps auf HoloLens</span><span class="sxs-lookup"><span data-stu-id="4b25d-115">Package Family Names for apps on HoloLens</span></span>

<span data-ttu-id="4b25d-116">In der oben verlinkten Anleitung können Sie newPolicy.xml manuell bearbeiten und Regeln für Anwendungen hinzufügen, die nur auf HoloLens mit ihren Paketfamiliennamen installiert sind.</span><span class="sxs-lookup"><span data-stu-id="4b25d-116">In the guide linked above, you can manually edit newPolicy.xml and add rules for applications that are only installed on HoloLens with their package family names.</span></span> <span data-ttu-id="4b25d-117">Manchmal gibt es Apps, die Sie verwenden können, die sich nicht auf Ihrem Desktop-PC befinden, die Sie der Richtlinie hinzufügen möchten.</span><span class="sxs-lookup"><span data-stu-id="4b25d-117">Sometimes there are apps you may use to use that are not on your desktop PC that you wish to add to policy.</span></span>

<span data-ttu-id="4b25d-118">Hier finden Sie eine Liste der häufig verwendeten und In-Box Apps für HoloLens 2 Geräte.</span><span class="sxs-lookup"><span data-stu-id="4b25d-118">Here is a list of commonly used and In-Box apps for HoloLens 2 devices.</span></span>

| <span data-ttu-id="4b25d-119">App-Name</span><span class="sxs-lookup"><span data-stu-id="4b25d-119">App Name</span></span>                   | <span data-ttu-id="4b25d-120">Paketfamilienname</span><span class="sxs-lookup"><span data-stu-id="4b25d-120">Package Family Name</span></span>                                |
|----------------------------|----------------------------------------------------|
| <span data-ttu-id="4b25d-121">3D-Viewer</span><span class="sxs-lookup"><span data-stu-id="4b25d-121">3D Viewer</span></span>                  | <span data-ttu-id="4b25d-122">Microsoft.Microsoft3DViewer_8wekyb3d8bbwe</span><span class="sxs-lookup"><span data-stu-id="4b25d-122">Microsoft.Microsoft3DViewer_8wekyb3d8bbwe</span></span>          |
| <span data-ttu-id="4b25d-123">App-Installer</span><span class="sxs-lookup"><span data-stu-id="4b25d-123">App Installer</span></span>              | <span data-ttu-id="4b25d-124">Microsoft.DesktopAppInstaller_8wekyb3d8bbwe <sup>1</sup></span><span class="sxs-lookup"><span data-stu-id="4b25d-124">Microsoft.DesktopAppInstaller_8wekyb3d8bbwe <sup>1</sup></span></span>         |
| <span data-ttu-id="4b25d-125">Calendar</span><span class="sxs-lookup"><span data-stu-id="4b25d-125">Calendar</span></span>                   | <span data-ttu-id="4b25d-126">microsoft.windowscommunicationsapps_8wekyb3d8bbwe</span><span class="sxs-lookup"><span data-stu-id="4b25d-126">microsoft.windowscommunicationsapps_8wekyb3d8bbwe</span></span>  |
| <span data-ttu-id="4b25d-127">Kamera</span><span class="sxs-lookup"><span data-stu-id="4b25d-127">Camera</span></span>                     | <span data-ttu-id="4b25d-128">HoloCamera_cw5n1h2txyewy</span><span class="sxs-lookup"><span data-stu-id="4b25d-128">HoloCamera_cw5n1h2txyewy</span></span>                           |
| <span data-ttu-id="4b25d-129">Cortana</span><span class="sxs-lookup"><span data-stu-id="4b25d-129">Cortana</span></span>                    | <span data-ttu-id="4b25d-130">Microsoft.549981C3F5F10_8wekyb3d8bbwe</span><span class="sxs-lookup"><span data-stu-id="4b25d-130">Microsoft.549981C3F5F10_8wekyb3d8bbwe</span></span>              |
| <span data-ttu-id="4b25d-131">Dynamics 365-Leitfäden</span><span class="sxs-lookup"><span data-stu-id="4b25d-131">Dynamics 365 Guides</span></span>        | <span data-ttu-id="4b25d-132">Microsoft.Dynamics365.Guides_8wekyb3d8bbwe</span><span class="sxs-lookup"><span data-stu-id="4b25d-132">Microsoft.Dynamics365.Guides_8wekyb3d8bbwe</span></span>         |
| <span data-ttu-id="4b25d-133">Dynamics 365 Remote Assist</span><span class="sxs-lookup"><span data-stu-id="4b25d-133">Dynamics 365 Remote Assist</span></span> | <span data-ttu-id="4b25d-134">Microsoft.MicrosoftRemoteAssist_8wekyb3d8bbwe</span><span class="sxs-lookup"><span data-stu-id="4b25d-134">Microsoft.MicrosoftRemoteAssist_8wekyb3d8bbwe</span></span>      |
| <span data-ttu-id="4b25d-135">Feedback-Hub</span><span class="sxs-lookup"><span data-stu-id="4b25d-135">Feedback Hub</span></span>               | <span data-ttu-id="4b25d-136">Microsoft.WindowsFeedbackHub_8wekyb3d8bbwe</span><span class="sxs-lookup"><span data-stu-id="4b25d-136">Microsoft.WindowsFeedbackHub_8wekyb3d8bbwe</span></span>         |
| <span data-ttu-id="4b25d-137">Datei-Explorer</span><span class="sxs-lookup"><span data-stu-id="4b25d-137">File Explorer</span></span>              | <span data-ttu-id="4b25d-138">c5e2524a-ea46-4f67-841f-6a9465d9d515_cw5n1h2txyewy</span><span class="sxs-lookup"><span data-stu-id="4b25d-138">c5e2524a-ea46-4f67-841f-6a9465d9d515_cw5n1h2txyewy</span></span> |
| <span data-ttu-id="4b25d-139">E-Mail</span><span class="sxs-lookup"><span data-stu-id="4b25d-139">Mail</span></span>                       | <span data-ttu-id="4b25d-140">microsoft.windowscommunicationsapps_8wekyb3d8bbwe</span><span class="sxs-lookup"><span data-stu-id="4b25d-140">microsoft.windowscommunicationsapps_8wekyb3d8bbwe</span></span>  |
| <span data-ttu-id="4b25d-141">Microsoft Store</span><span class="sxs-lookup"><span data-stu-id="4b25d-141">Microsoft Store</span></span>            | <span data-ttu-id="4b25d-142">Microsoft.WindowsStore_8wekyb3d8bbwe</span><span class="sxs-lookup"><span data-stu-id="4b25d-142">Microsoft.WindowsStore_8wekyb3d8bbwe</span></span>               |
| <span data-ttu-id="4b25d-143">Filme & TV</span><span class="sxs-lookup"><span data-stu-id="4b25d-143">Movies & TV</span></span>                | <span data-ttu-id="4b25d-144">Microsoft.ZuneVideo_8wekyb3d8bbwe</span><span class="sxs-lookup"><span data-stu-id="4b25d-144">Microsoft.ZuneVideo_8wekyb3d8bbwe</span></span>                  |
| <span data-ttu-id="4b25d-145">OneDrive</span><span class="sxs-lookup"><span data-stu-id="4b25d-145">OneDrive</span></span>                   | <span data-ttu-id="4b25d-146">microsoft.microsoftskydrive_8wekyb3d8bbwe</span><span class="sxs-lookup"><span data-stu-id="4b25d-146">microsoft.microsoftskydrive_8wekyb3d8bbwe</span></span>          |
| <span data-ttu-id="4b25d-147">Fotos</span><span class="sxs-lookup"><span data-stu-id="4b25d-147">Photos</span></span>                     | <span data-ttu-id="4b25d-148">Microsoft. Windows. Photos_8wekyb3d8bbwe</span><span class="sxs-lookup"><span data-stu-id="4b25d-148">Microsoft.Windows.Photos_8wekyb3d8bbwe</span></span>             |
| <span data-ttu-id="4b25d-149">Einstellungen</span><span class="sxs-lookup"><span data-stu-id="4b25d-149">Settings</span></span>                   | <span data-ttu-id="4b25d-150">HolographicSystemSettings_cw5n1h2txyewy</span><span class="sxs-lookup"><span data-stu-id="4b25d-150">HolographicSystemSettings_cw5n1h2txyewy</span></span>            |
| <span data-ttu-id="4b25d-151">Tipps</span><span class="sxs-lookup"><span data-stu-id="4b25d-151">Tips</span></span>                       | <span data-ttu-id="4b25d-152">Microsoft.HoloLensTips_8wekyb3d8bbwe</span><span class="sxs-lookup"><span data-stu-id="4b25d-152">Microsoft.HoloLensTips_8wekyb3d8bbwe</span></span>               |

- <span data-ttu-id="4b25d-153">1– Durch blockierende App-Installer wird nur die App-Installer-App blockiert, nicht die Apps, die aus anderen Quellen wie dem Microsoft Store oder aus Ihrer MDM-Lösung installiert wurden.</span><span class="sxs-lookup"><span data-stu-id="4b25d-153">1 - Blocking App Installer will only block the App Installer app, and not apps installed from other sources such as the Microsoft Store or from your MDM solution.</span></span>

### <a name="how-to-find-a-package-family-name"></a><span data-ttu-id="4b25d-154">Suchen eines Paketfamiliennamens</span><span class="sxs-lookup"><span data-stu-id="4b25d-154">How to find a Package Family Name</span></span>

<span data-ttu-id="4b25d-155">Wenn eine App nicht in dieser Liste enthalten ist, kann ein Benutzer Geräteportal verwenden, der mit einem HoloLens 2 verbunden ist, der die App installiert hat, die blockiert werden soll, um die PackageRelativeID zu bestimmen und von dort den PackageFamilyName abzurufen.</span><span class="sxs-lookup"><span data-stu-id="4b25d-155">If an app is not on this list, then a user may use Device Portal, connected to a HoloLens 2 that has installed the app wished to be blocked, to determine the PackageRelativeID and from there get the PackageFamilyName.</span></span>

1. <span data-ttu-id="4b25d-156">Installieren Sie die App auf Ihrem HoloLens 2 Gerät.</span><span class="sxs-lookup"><span data-stu-id="4b25d-156">Install the app on your HoloLens 2 device.</span></span> 
1. <span data-ttu-id="4b25d-157">Öffnen Sie Einstellungen -> Updates & Security -> Für Entwickler, aktivieren Sie den **Entwicklermodus** und dann das **Geräteportal.**</span><span class="sxs-lookup"><span data-stu-id="4b25d-157">Open Settings -> Updates & Security -> For developers, and enable **Developer mode** and then **Device portal**.</span></span> 
    1. <span data-ttu-id="4b25d-158">Ausführlichere Anweisungen zum [Einrichten und Verwenden des Geräteportals finden Sie hier.](/windows/mixed-reality/develop/platform-capabilities-and-apis/using-the-windows-device-portal)</span><span class="sxs-lookup"><span data-stu-id="4b25d-158">More more details instructions read more about [setup and use of device portal here](/windows/mixed-reality/develop/platform-capabilities-and-apis/using-the-windows-device-portal).</span></span>
1. <span data-ttu-id="4b25d-159">Sobald Geräteportal verbunden ist, navigieren Sie zu **Ansichten** und dann **zu Apps.**</span><span class="sxs-lookup"><span data-stu-id="4b25d-159">Once Device Portal is connected, navigate to **Views** then **Apps**.</span></span> 
1. <span data-ttu-id="4b25d-160">Wählen Sie im Bereich Installierte Apps die Dropdownliste aus, um die installierte App auszuwählen.</span><span class="sxs-lookup"><span data-stu-id="4b25d-160">Within the Installed Apps panel, use the dropdown to select the installed app.</span></span> 
1. <span data-ttu-id="4b25d-161">Suchen Sie packageRelativeID.</span><span class="sxs-lookup"><span data-stu-id="4b25d-161">Locate the PackageRelativeID.</span></span> 
1. <span data-ttu-id="4b25d-162">Kopieren Sie App-Zeichen vor !. Diese Zeichen sind Ihr PackageFamilyName.</span><span class="sxs-lookup"><span data-stu-id="4b25d-162">Copy app characters before the !, these characters will be your PackageFamilyName.</span></span>


