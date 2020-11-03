---
title: Herunterladen und Installieren von apps über das HoloLens 2-App-Installationsprogramm
description: Laden und Installieren von apps über die Benutzeroberfläche
keywords: App-Verwaltung, APP, hololens, App-Installationsprogramm
author: evmill
ms.author: v-evmill
ms.reviewer: qizho
ms.date: 10/26/2020
ms.prod: hololens
ms.topic: article
ms.sitesec: library
ms.localizationpriority: medium
audience: HoloLens
manager: yannisle
appliesto:
- HoloLens 2
ms.openlocfilehash: 415733bb2809b7ae2808edc097423f8928910c57
ms.sourcegitcommit: c4fd9a87bb7c728c73418f95a1b15dd93b0af7c6
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/03/2020
ms.locfileid: "11150916"
---
# <span data-ttu-id="36338-104">Installieren von apps auf HoloLens 2 über das App-Installationsprogramm</span><span class="sxs-lookup"><span data-stu-id="36338-104">Install Apps on HoloLens 2 via App Installer</span></span>

> [!IMPORTANT]
> <span data-ttu-id="36338-105">Dieses Feature ist derzeit nur avalible in Windows Insider-Builds 19041.1377 +.</span><span class="sxs-lookup"><span data-stu-id="36338-105">This feature is currently only avalible in Windows Insider builds 19041.1377+.</span></span> <span data-ttu-id="36338-106">[Weitere Informationen zum Registrieren von Windows Insider-Builds](hololens-insider.md).</span><span class="sxs-lookup"><span data-stu-id="36338-106">[Learn more on how to enroll in Windows Insider builds](hololens-insider.md).</span></span>

<span data-ttu-id="36338-107">In unserer Windows-Insider-Version **fügen wir eine neue Funktion (app-Installationsprogramm) hinzu, mit der Sie Anwendungen nahtlos** auf Ihren HoloLens 2-Geräten installieren können.</span><span class="sxs-lookup"><span data-stu-id="36338-107">In our Windows Insider release, we are **adding a new capability (App Installer) to allow you to install applications more seamlessly** on your HoloLens 2 devices.</span></span> <span data-ttu-id="36338-108">Das Feature ist **für nicht verwaltete Geräte standardmäßig aktiviert**.</span><span class="sxs-lookup"><span data-stu-id="36338-108">The feature will be **on by default for unmanaged devices**.</span></span> <span data-ttu-id="36338-109">Um Unterbrechungen von Unternehmen zu verhindern, steht das App-Installationsprogramm derzeit **nicht für verwaltete Geräte zur Verfügung** .</span><span class="sxs-lookup"><span data-stu-id="36338-109">To prevent disruption to enterprises, app installer will be **not be available for managed devices** at this time.</span></span>  

<span data-ttu-id="36338-110">Ein Gerät gilt als "verwaltet", **Wenn eine der folgenden** Bedingungen zutrifft:</span><span class="sxs-lookup"><span data-stu-id="36338-110">A device is considered “managed” if **any** of the following are true:</span></span>
- <span data-ttu-id="36338-111">MDM [registriert](hololens-enroll-mdm.md)</span><span class="sxs-lookup"><span data-stu-id="36338-111">MDM [Enrolled](hololens-enroll-mdm.md)</span></span>
- <span data-ttu-id="36338-112">Mit [Bereitstellungspaket](hololens-provisioning.md) konfiguriert</span><span class="sxs-lookup"><span data-stu-id="36338-112">Configured with [provisioning package](hololens-provisioning.md)</span></span>
- <span data-ttu-id="36338-113">Benutzer [Identität](hololens-identity.md) ist Aad</span><span class="sxs-lookup"><span data-stu-id="36338-113">User [Identity](hololens-identity.md) is AAD</span></span>

<span data-ttu-id="36338-114">Sie können jetzt apps installieren, ohne den Entwicklermodus oder die Verwendung des Geräte Portals aktivieren zu müssen.</span><span class="sxs-lookup"><span data-stu-id="36338-114">You are now able to install Apps without needing to enable Developer Mode or using Device Portal.</span></span>  <span data-ttu-id="36338-115">Laden Sie einfach (über USB oder durch Edge) das AppX-Paket auf Ihr Gerät herunter, und navigieren Sie im Datei-Explorer zum AppX-Paket, um aufgefordert zu werden, die Installation zu starten.</span><span class="sxs-lookup"><span data-stu-id="36338-115">Simply download (over USB or through Edge) the Appx Bundle to your device and navigate to the Appx Bundle in the File Explorer to be prompted to kick off the installation.</span></span>  <span data-ttu-id="36338-116">Alternativ können Sie [eine Installation von einer Webseite aus initiieren](https://docs.microsoft.com/windows/msix/app-installer/installing-windows10-apps-web).</span><span class="sxs-lookup"><span data-stu-id="36338-116">Alternatively, [initiate an install from a web page](https://docs.microsoft.com/windows/msix/app-installer/installing-windows10-apps-web).</span></span>  <span data-ttu-id="36338-117">Genau wie apps, die Sie über den Microsoft Store oder querladen mit der Dienst Bereitstellungsfunktion der Branchen-App für die Branchenanwendung von MDM installieren, müssen apps mit dem [Signatur Tool](https://docs.microsoft.com/windows/win32/appxpkg/how-to-sign-a-package-using-signtool) digital signiert werden, und das [zum Signieren verwendete Zertifikat muss](https://docs.microsoft.com/windows/win32/appxpkg/how-to-sign-a-package-using-signtool#security-considerations) vom HoloLens-Gerät als vertrauenswürdig eingestuft werden, bevor die APP bereitgestellt werden kann.</span><span class="sxs-lookup"><span data-stu-id="36338-117">Just like apps you install from the Microsoft Store or sideload using MDM’s LOB App deployment capability, apps need to be digitally signed with the [Sign Tool](https://docs.microsoft.com/windows/win32/appxpkg/how-to-sign-a-package-using-signtool) and the [certificate used to sign must be trusted](https://docs.microsoft.com/windows/win32/appxpkg/how-to-sign-a-package-using-signtool#security-considerations) by the HoloLens device before the app can be deployed.</span></span>   

## <span data-ttu-id="36338-118">Anforderungen</span><span class="sxs-lookup"><span data-stu-id="36338-118">Requirements</span></span>

### <span data-ttu-id="36338-119">Für Ihre Geräte:</span><span class="sxs-lookup"><span data-stu-id="36338-119">For your devices:</span></span> 
> [!NOTE]
> <span data-ttu-id="36338-120">Dieses Feature ist derzeit nur avalible in Windows Insider-Builds 19041.1377 +.</span><span class="sxs-lookup"><span data-stu-id="36338-120">This feature is currently only avalible in Windows Insider builds 19041.1377+.</span></span> <span data-ttu-id="36338-121">[Weitere Informationen zum Registrieren von Windows Insider-Builds](hololens-insider.md).</span><span class="sxs-lookup"><span data-stu-id="36338-121">[Learn more on how to enroll in Windows Insider builds](hololens-insider.md).</span></span>

### <span data-ttu-id="36338-122">Für Ihre apps:</span><span class="sxs-lookup"><span data-stu-id="36338-122">For your apps:</span></span> 
<span data-ttu-id="36338-123">Die Projektmappenkonfiguration der APP muss entweder **Master** oder **Release** sein, da vom APP-Installationsprogramm Abhängigkeiten aus dem Store verwendet werden.</span><span class="sxs-lookup"><span data-stu-id="36338-123">Your app’s Solution Configuration must be either **Master** or **Release** as the App Installer will use dependencies from the store.</span></span> <span data-ttu-id="36338-124">Weitere Informationen finden Sie unter [Erstellen von App-Paketen](https://docs.microsoft.com/windows/msix/app-installer/create-appinstallerfile-vs).</span><span class="sxs-lookup"><span data-stu-id="36338-124">See more about [creating app packages](https://docs.microsoft.com/windows/msix/app-installer/create-appinstallerfile-vs).</span></span>

<span data-ttu-id="36338-125">Apps, die über diese Methode installiert werden, müssen digital signiert sein.</span><span class="sxs-lookup"><span data-stu-id="36338-125">Apps that are installed via this method must be digitally signed.</span></span> <span data-ttu-id="36338-126">Sie müssen ein Zertifikat zum Signieren der App verwenden.</span><span class="sxs-lookup"><span data-stu-id="36338-126">You'll need to use a certificate to sign the app.</span></span> <span data-ttu-id="36338-127">Sie können entweder ein Zertifikat aus der [Liste der vertrauenswürdigen MS-Zertifizierungsstelle](https://ccadb-public.secure.force.com/microsoft/IncludedCACertificateReportForMSFT)anfordern, in diesem Fall müssen Sie keine weiteren Schritte Unternehmen.</span><span class="sxs-lookup"><span data-stu-id="36338-127">You can either get a certificate from the [MS Trusted CA List](https://ccadb-public.secure.force.com/microsoft/IncludedCACertificateReportForMSFT), in which case you won't need to take any additional action.</span></span> <span data-ttu-id="36338-128">Oder Sie können ein eigenes Zertifikat signieren, das Zertifikat muss jedoch auf das Gerät übertragen werden.</span><span class="sxs-lookup"><span data-stu-id="36338-128">Or you can sign your own certificate however that certificate will need to be pushed onto the device.</span></span> 
- <span data-ttu-id="36338-129">Signieren [von apps mit dem Signatur Tool](https://docs.microsoft.com/windows/win32/appxpkg/how-to-sign-a-package-using-signtool)</span><span class="sxs-lookup"><span data-stu-id="36338-129">How to sign apps [using the Sign Tool.](https://docs.microsoft.com/windows/win32/appxpkg/how-to-sign-a-package-using-signtool)</span></span>

**<span data-ttu-id="36338-130">Zertifikatoptionen:</span><span class="sxs-lookup"><span data-stu-id="36338-130">Certificate options:</span></span>** 
- [<span data-ttu-id="36338-131">Liste der vertrauenswürdigen MS-Zertifizierungsstelle</span><span class="sxs-lookup"><span data-stu-id="36338-131">MS Trusted CA List</span></span>](https://ccadb-public.secure.force.com/microsoft/IncludedCACertificateReportForMSFT)

**<span data-ttu-id="36338-132">Entscheiden Sie sich für eine Zertifikat Bereitstellungsmethode.</span><span class="sxs-lookup"><span data-stu-id="36338-132">Pick a certificate deployment method.</span></span>** 
- <span data-ttu-id="36338-133">[Bereitstellungspakete](hololens-provisioning.md) können auf lokale Geräte angewendet werden.</span><span class="sxs-lookup"><span data-stu-id="36338-133">[Provisioning Packages](hololens-provisioning.md) can be applied to local devices.</span></span>
- <span data-ttu-id="36338-134">MDM kann verwendet werden, um [Zertifikate mit Gerätekonfigurationen anzuwenden](https://docs.microsoft.com/mem/intune/protect/certificates-configure).</span><span class="sxs-lookup"><span data-stu-id="36338-134">MDM can be used to [apply certificates with device configurations](https://docs.microsoft.com/mem/intune/protect/certificates-configure).</span></span>
- <span data-ttu-id="36338-135">Verwenden Sie den [Zertifikat-Manager](hololens-insider.md#certificate-manager)für Geräte.</span><span class="sxs-lookup"><span data-stu-id="36338-135">Use the on device [Certificate Manager](hololens-insider.md#certificate-manager).</span></span> 

## <span data-ttu-id="36338-136">Installationsmethode</span><span class="sxs-lookup"><span data-stu-id="36338-136">Installation method</span></span>

1.  <span data-ttu-id="36338-137">Stellen Sie sicher, dass Ihr Gerät nicht als verwaltet angesehen wird.</span><span class="sxs-lookup"><span data-stu-id="36338-137">Ensure that your device is not considered managed.</span></span>
1.  <span data-ttu-id="36338-138">Stellen Sie sicher, dass Ihr HoloLens 2-Gerät eingeschaltet ist und Sie angemeldet sind.</span><span class="sxs-lookup"><span data-stu-id="36338-138">Ensure that your HoloLens 2 device is powered on and you are signed in.</span></span>
1.  <span data-ttu-id="36338-139">Navigieren Sie auf Ihrem PC zu Ihrer benutzerdefinierten APP, und kopieren Sie yourapp. appxbundle nach yourdevicename\Internal Storage\Downloads.</span><span class="sxs-lookup"><span data-stu-id="36338-139">On your PC navigate to your custom app, and copy yourapp.appxbundle to yourdevicename\Internal Storage\Downloads.</span></span> 
    <span data-ttu-id="36338-140">Nachdem Sie Ihre Datei fertig kopiert haben, können Sie Ihr Gerät trennen und die Installation später abschließen.</span><span class="sxs-lookup"><span data-stu-id="36338-140">After your finish copying your file you may disconnect your device and finish the install later.</span></span>
1.  <span data-ttu-id="36338-141">Öffnen Sie auf Ihrem HoloLens 2-Gerät das **Startmenü**, wählen Sie **alle apps** aus, und starten Sie die **Datei-Explorer** -app.</span><span class="sxs-lookup"><span data-stu-id="36338-141">From your HoloLens 2 device Open the **Start Menu**, select **All apps** and launch the **File Explorer** app.</span></span>
1.  <span data-ttu-id="36338-142">Navigieren Sie zum Ordner Downloads.</span><span class="sxs-lookup"><span data-stu-id="36338-142">Navigate to the Downloads folder.</span></span> <span data-ttu-id="36338-143">Möglicherweise müssen Sie auf der linken Seite der APP zuerst **dieses Gerät** auswählen und dann zu Downloads navigieren.</span><span class="sxs-lookup"><span data-stu-id="36338-143">You may need to on the left panel of the app select **This device** first, then navigate to Downloads.</span></span>
1.  <span data-ttu-id="36338-144">Wählen Sie die Datei "yourapp. appxbundle" aus.</span><span class="sxs-lookup"><span data-stu-id="36338-144">Select the yourapp.appxbundle file.</span></span> 
1.  <span data-ttu-id="36338-145">Das App-Installationsprogramm wird gestartet.</span><span class="sxs-lookup"><span data-stu-id="36338-145">The App Installer will launch.</span></span> <span data-ttu-id="36338-146">Wählen Sie die Schaltfläche **Installieren** aus, um Ihre APP zu installieren.</span><span class="sxs-lookup"><span data-stu-id="36338-146">Select the **Install** button to install your app.</span></span> 

<span data-ttu-id="36338-147">Die installierte APP wird nach Abschluss der Installation automatisch gestartet.</span><span class="sxs-lookup"><span data-stu-id="36338-147">The installed app will automatically launch upon the completion of installing.</span></span> 

![Installieren von MRTK-Beispielen über das App-Installationsprogramm](images/hololens-app-installer-picture.jpg)

### <span data-ttu-id="36338-149">Problembehandlung bei Installationen</span><span class="sxs-lookup"><span data-stu-id="36338-149">Troubleshooting Installs</span></span>
<span data-ttu-id="36338-150">Wenn Ihre APP nicht installiert werden konnte, prüfen Sie Folgendes:</span><span class="sxs-lookup"><span data-stu-id="36338-150">If your app failed to install check the following:</span></span>
-   <span data-ttu-id="36338-151">Ihre APP ist entweder ein Master-oder Release-Build.</span><span class="sxs-lookup"><span data-stu-id="36338-151">Your app is either a Master or Release build.</span></span>
- <span data-ttu-id="36338-152">Ihr Gerät wird auf einen Build aktualisiert, auf dem dieses Feature verfügbar ist.</span><span class="sxs-lookup"><span data-stu-id="36338-152">Your device is updated to a build on which this feature is available.</span></span> 
-   <span data-ttu-id="36338-153">Sie sind [mit dem Internet verbunden](hololens-network.md).</span><span class="sxs-lookup"><span data-stu-id="36338-153">You are [connected to the internet](hololens-network.md).</span></span>
-   <span data-ttu-id="36338-154">Ihre [Endpunkte für den Microsoft Store](hololens-offline.md) sind ordnungsgemäß konfiguriert.</span><span class="sxs-lookup"><span data-stu-id="36338-154">Your [endpoints for the Microsoft Store](hololens-offline.md) are correctly configured.</span></span>  

## <span data-ttu-id="36338-155">Web Installer</span><span class="sxs-lookup"><span data-stu-id="36338-155">Web Installer</span></span>

<span data-ttu-id="36338-156">Benutzer können eine APP direkt von einem Webserver installieren.</span><span class="sxs-lookup"><span data-stu-id="36338-156">Users can install an app directly from a web server.</span></span> <span data-ttu-id="36338-157">Dadurch wird das App-Installationsprogramm in Kombination mit einer einfachen Download-und Installations Verteilungsmethode verwendet.</span><span class="sxs-lookup"><span data-stu-id="36338-157">This takes use of the App Installer combined with an easy download and install distribution method.</span></span> 

### <span data-ttu-id="36338-158">Einrichten der Web-Installation:</span><span class="sxs-lookup"><span data-stu-id="36338-158">How to set up web install:</span></span>
1.  <span data-ttu-id="36338-159">Stellen Sie sicher, dass Ihre APP für die Installation richtig konfiguriert ist.</span><span class="sxs-lookup"><span data-stu-id="36338-159">Ensure your app is correctly configured to install.</span></span>
1.  <span data-ttu-id="36338-160">Führen Sie die folgenden [Schritte aus, um diese auf einer Webseite zu aktivieren](https://docs.microsoft.com/windows/msix/app-installer/installing-windows10-apps-web#how-to-enable-this-on-a-webpage).</span><span class="sxs-lookup"><span data-stu-id="36338-160">Follow these [steps to enable this on a web page](https://docs.microsoft.com/windows/msix/app-installer/installing-windows10-apps-web#how-to-enable-this-on-a-webpage).</span></span> 

### <span data-ttu-id="36338-161">Benutzerfreundlichkeit:</span><span class="sxs-lookup"><span data-stu-id="36338-161">End user experience:</span></span>
1. <span data-ttu-id="36338-162">Der Benutzer empfängt und installiert das Zertifikat auf dem Gerät mithilfe einer zuvor ausgewählten Methode.</span><span class="sxs-lookup"><span data-stu-id="36338-162">User receives and installs certificate to the device using a method previously chosen above.</span></span> 
1. <span data-ttu-id="36338-163">Der Benutzer besucht die URL, die aus dem obigen Schritt erstellt wurde.</span><span class="sxs-lookup"><span data-stu-id="36338-163">User visits the URL created from the step above.</span></span>

<span data-ttu-id="36338-164">Die APP wird nun auf dem Gerät installiert.</span><span class="sxs-lookup"><span data-stu-id="36338-164">The app will now install to the device.</span></span> <span data-ttu-id="36338-165">Um die APP zu finden, öffnen Sie das **Startmenü** , und wählen Sie die Schaltfläche **alle apps** aus, um Ihre APP zu finden.</span><span class="sxs-lookup"><span data-stu-id="36338-165">To find the app open the **Start menu** and select the **All apps** button to find your app.</span></span> 

-   <span data-ttu-id="36338-166">Hilfe zur Problembehandlung dieser Installationsmethode finden Sie unter [Problembehandlung von Problemen mit dem App-Installationsprogramm](https://docs.microsoft.com/windows/msix/app-installer/troubleshoot-appinstaller-issues).</span><span class="sxs-lookup"><span data-stu-id="36338-166">For help troubleshooting this installation method please visit [troubleshoot app installer issues](https://docs.microsoft.com/windows/msix/app-installer/troubleshoot-appinstaller-issues).</span></span> 

> [!NOTE]
> <span data-ttu-id="36338-167">Die Benutzeroberfläche wird während des Aktualisierungsvorgangs nicht unterstützt.</span><span class="sxs-lookup"><span data-stu-id="36338-167">UI during the update process is not supported.</span></span> <span data-ttu-id="36338-168">Daher werden die ShowPrompt-Option auf [dieser Seite](https://docs.microsoft.com/windows/msix/app-installer/update-settings) und die zugehörigen Optionen nicht unterstützt.</span><span class="sxs-lookup"><span data-stu-id="36338-168">So the ShowPrompt option on [this page](https://docs.microsoft.com/windows/msix/app-installer/update-settings) and related options are not supported.</span></span>

## <span data-ttu-id="36338-169">Beispiel-apps</span><span class="sxs-lookup"><span data-stu-id="36338-169">Sample Apps</span></span>

<span data-ttu-id="36338-170">Wenn Sie dies mit einigen Beispiel-apps ausprobieren möchten, schauen Sie sich einige unserer verfügbaren Beispiele an:</span><span class="sxs-lookup"><span data-stu-id="36338-170">If you'd like to try this out with some sample apps please check out some of our available samples:</span></span>
- [<span data-ttu-id="36338-171">MRTK examples Hub</span><span class="sxs-lookup"><span data-stu-id="36338-171">MRTK Examples Hub</span></span>](https://microsoft.github.io/MixedRealityToolkit-Unity/Documentation/README_ExampleHub.html)
- [<span data-ttu-id="36338-172">Flächen</span><span class="sxs-lookup"><span data-stu-id="36338-172">Surfaces</span></span>](https://docs.microsoft.com/windows/mixed-reality/develop/unity/sampleapp-surfaces)
- [<span data-ttu-id="36338-173">UWP-Beispiel-apps, die für Tests verwendet werden können</span><span class="sxs-lookup"><span data-stu-id="36338-173">UWP Sample Apps that can be used for testing</span></span>](https://github.com/microsoft/Windows-universal-samples/tree/master/Samples)
