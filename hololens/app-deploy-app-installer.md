---
title: Herunterladen und Installieren von apps über das HoloLens 2-App-Installationsprogramm
description: Laden und Installieren von apps über die Benutzeroberfläche
keywords: App-Verwaltung, APP, hololens, App-Installationsprogramm
author: evmill
ms.author: v-evmill
ms.reviewer: qizho
ms.date: 11/10/2020
ms.prod: hololens
ms.topic: article
ms.sitesec: library
ms.localizationpriority: medium
audience: HoloLens
manager: yannisle
appliesto:
- HoloLens 2
ms.openlocfilehash: e52cc2f031c284b619c61ffa04f259f76397faf5
ms.sourcegitcommit: 96dcd015ad24169295690a8ed13ea1bf480e4b9e
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 01/01/2021
ms.locfileid: "11253092"
---
# <span data-ttu-id="1fedb-104">Installieren von apps auf HoloLens 2 über das App-Installationsprogramm</span><span class="sxs-lookup"><span data-stu-id="1fedb-104">Install Apps on HoloLens 2 via App Installer</span></span>

<span data-ttu-id="1fedb-105">Wir **fügen eine neue Funktion (app-Installationsprogramm) hinzu, mit der Sie Anwendungen nahtlos** auf Ihren HoloLens 2-Geräten installieren können.</span><span class="sxs-lookup"><span data-stu-id="1fedb-105">We are **adding a new capability (App Installer) to allow you to install applications more seamlessly** on your HoloLens 2 devices.</span></span> <span data-ttu-id="1fedb-106">Das Feature ist **für nicht verwaltete Geräte standardmäßig aktiviert**.</span><span class="sxs-lookup"><span data-stu-id="1fedb-106">The feature will be **on by default for unmanaged devices**.</span></span> <span data-ttu-id="1fedb-107">Um Unterbrechungen von Unternehmen zu verhindern, steht das App-Installationsprogramm derzeit **nicht für verwaltete Geräte zur Verfügung** .</span><span class="sxs-lookup"><span data-stu-id="1fedb-107">To prevent disruption to enterprises, app installer will **not be available for managed devices** at this time.</span></span>  

> [!NOTE]
> <span data-ttu-id="1fedb-108">Dieses Feature wurde in [Windows holographisch, Version 20H2 – Dezember 2020-Update](hololens-release-notes.md)zur Verfügung gestellt.</span><span class="sxs-lookup"><span data-stu-id="1fedb-108">This feature was made available in [Windows Holographic, version 20H2 – December 2020 Update](hololens-release-notes.md).</span></span> <span data-ttu-id="1fedb-109">Stellen Sie sicher, dass Ihr Gerät [aktualisiert](hololens-update-hololens.md) wurde, um dieses Feature zu verwenden.</span><span class="sxs-lookup"><span data-stu-id="1fedb-109">Ensure your device is [updated](hololens-update-hololens.md) to use this feature.</span></span>

<span data-ttu-id="1fedb-110">Wir haben **eine neue Funktion (app-Installationsprogramm) hinzugefügt, mit der Sie Anwendungen nahtlos** auf Ihren HoloLens 2-Geräten installieren können.</span><span class="sxs-lookup"><span data-stu-id="1fedb-110">We have **added a new capability (App Installer) to allow you to install applications more seamlessly** on your HoloLens 2 devices.</span></span> <span data-ttu-id="1fedb-111">Das Feature ist **für nicht verwaltete Geräte standardmäßig aktiviert**.</span><span class="sxs-lookup"><span data-stu-id="1fedb-111">The feature will be **on by default for unmanaged devices**.</span></span> <span data-ttu-id="1fedb-112">Um Unterbrechungen von Unternehmen zu verhindern, steht das App-Installationsprogramm derzeit **nicht für verwaltete Geräte zur Verfügung** .</span><span class="sxs-lookup"><span data-stu-id="1fedb-112">To prevent disruption to enterprises, app installer will be **not be available for managed devices** at this time.</span></span>  

<span data-ttu-id="1fedb-113">Ein Gerät gilt als "verwaltet", **Wenn eine der folgenden** Bedingungen zutrifft:</span><span class="sxs-lookup"><span data-stu-id="1fedb-113">A device is considered “managed” if **any** of the following are true:</span></span>

- <span data-ttu-id="1fedb-114">MDM [registriert](hololens-enroll-mdm.md)</span><span class="sxs-lookup"><span data-stu-id="1fedb-114">MDM [Enrolled](hololens-enroll-mdm.md)</span></span>
- <span data-ttu-id="1fedb-115">Mit [Bereitstellungspaket](hololens-provisioning.md) konfiguriert</span><span class="sxs-lookup"><span data-stu-id="1fedb-115">Configured with [provisioning package](hololens-provisioning.md)</span></span>
- <span data-ttu-id="1fedb-116">Benutzer [Identität](hololens-identity.md) ist Azure AD</span><span class="sxs-lookup"><span data-stu-id="1fedb-116">User [Identity](hololens-identity.md) is Azure AD</span></span>

<span data-ttu-id="1fedb-117">Sie können jetzt apps installieren, ohne den Entwicklermodus oder die Verwendung des Geräte Portals aktivieren zu müssen.</span><span class="sxs-lookup"><span data-stu-id="1fedb-117">You are now able to install Apps without needing to enable Developer Mode or using Device Portal.</span></span>  <span data-ttu-id="1fedb-118">Laden Sie (über USB oder über Microsoft Edge) das AppX-Paket auf Ihr Gerät herunter, und navigieren Sie im Datei-Explorer zum AppX-Paket, um aufgefordert zu werden, die Installation zu starten.</span><span class="sxs-lookup"><span data-stu-id="1fedb-118">Download (over USB or through Microsoft Edge) the Appx Bundle to your device and navigate to the Appx Bundle in the File Explorer to be prompted to kick off the installation.</span></span>  <span data-ttu-id="1fedb-119">Alternativ können Sie [eine Installation von einer Webseite aus initiieren](https://docs.microsoft.com/windows/msix/app-installer/installing-windows10-apps-web).</span><span class="sxs-lookup"><span data-stu-id="1fedb-119">Alternatively, [initiate an install from a web page](https://docs.microsoft.com/windows/msix/app-installer/installing-windows10-apps-web).</span></span>  <span data-ttu-id="1fedb-120">Genau wie apps, die Sie über den Microsoft Store oder querladen mit der Dienst Bereitstellungsfunktion der Branchen-App für die Branchenanwendung von MDM installieren, müssen apps mit dem [Signatur Tool](https://docs.microsoft.com/windows/win32/appxpkg/how-to-sign-a-package-using-signtool) digital signiert werden, und das [zum Signieren verwendete Zertifikat muss](https://docs.microsoft.com/windows/win32/appxpkg/how-to-sign-a-package-using-signtool#security-considerations) vom HoloLens-Gerät als vertrauenswürdig eingestuft werden, bevor die APP bereitgestellt werden kann.</span><span class="sxs-lookup"><span data-stu-id="1fedb-120">Just like apps you install from the Microsoft Store or sideload using MDM’s LOB App deployment capability, apps need to be digitally signed with the [Sign Tool](https://docs.microsoft.com/windows/win32/appxpkg/how-to-sign-a-package-using-signtool) and the [certificate used to sign must be trusted](https://docs.microsoft.com/windows/win32/appxpkg/how-to-sign-a-package-using-signtool#security-considerations) by the HoloLens device before the app can be deployed.</span></span>

## <span data-ttu-id="1fedb-121">Anforderungen</span><span class="sxs-lookup"><span data-stu-id="1fedb-121">Requirements</span></span>

### <span data-ttu-id="1fedb-122">Für Ihre Geräte:</span><span class="sxs-lookup"><span data-stu-id="1fedb-122">For your devices:</span></span>

 <span data-ttu-id="1fedb-123">Das Feature steht derzeit in Windows holographischen 20H2-Builds für HoloLens 2-Geräte zur Verfügung.</span><span class="sxs-lookup"><span data-stu-id="1fedb-123">feature is currently available in Windows Holographic 20H2 builds for HoloLens 2 devices.</span></span> <span data-ttu-id="1fedb-124">Stellen Sie sicher, dass alle Geräte, die diese Methode verwenden, [aktualisiert](hololens-update-hololens.md)werden.</span><span class="sxs-lookup"><span data-stu-id="1fedb-124">Ensure any devices using this method are [updated](hololens-update-hololens.md).</span></span>

### <span data-ttu-id="1fedb-125">Für Ihre apps:</span><span class="sxs-lookup"><span data-stu-id="1fedb-125">For your apps:</span></span> 
<span data-ttu-id="1fedb-126">Die Projektmappenkonfiguration der APP muss entweder **Master** oder **Release** sein, da vom APP-Installationsprogramm Abhängigkeiten aus dem Store verwendet werden.</span><span class="sxs-lookup"><span data-stu-id="1fedb-126">Your app’s Solution Configuration must be either **Master** or **Release** as the App Installer will use dependencies from the store.</span></span> <span data-ttu-id="1fedb-127">Weitere Informationen finden Sie unter [Erstellen von App-Paketen](https://docs.microsoft.com/windows/msix/app-installer/create-appinstallerfile-vs).</span><span class="sxs-lookup"><span data-stu-id="1fedb-127">See more about [creating app packages](https://docs.microsoft.com/windows/msix/app-installer/create-appinstallerfile-vs).</span></span>

<span data-ttu-id="1fedb-128">Apps, die über diese Methode installiert werden, müssen digital signiert sein.</span><span class="sxs-lookup"><span data-stu-id="1fedb-128">Apps that are installed via this method must be digitally signed.</span></span> <span data-ttu-id="1fedb-129">Sie müssen ein Zertifikat zum Signieren der App verwenden.</span><span class="sxs-lookup"><span data-stu-id="1fedb-129">You'll need to use a certificate to sign the app.</span></span> <span data-ttu-id="1fedb-130">Sie können entweder ein Zertifikat aus der [Liste der vertrauenswürdigen MS-Zertifizierungsstelle](https://ccadb-public.secure.force.com/microsoft/IncludedCACertificateReportForMSFT)anfordern, in diesem Fall müssen Sie keine weiteren Schritte Unternehmen.</span><span class="sxs-lookup"><span data-stu-id="1fedb-130">You can either get a certificate from the [MS Trusted CA List](https://ccadb-public.secure.force.com/microsoft/IncludedCACertificateReportForMSFT), in which case you won't need to take any additional action.</span></span> <span data-ttu-id="1fedb-131">Oder Sie können ein eigenes Zertifikat signieren, das Zertifikat muss jedoch auf das Gerät übertragen werden.</span><span class="sxs-lookup"><span data-stu-id="1fedb-131">Or you can sign your own certificate however that certificate will need to be pushed onto the device.</span></span>

- <span data-ttu-id="1fedb-132">Signieren [von apps mit dem Signatur Tool](https://docs.microsoft.com/windows/win32/appxpkg/how-to-sign-a-package-using-signtool)</span><span class="sxs-lookup"><span data-stu-id="1fedb-132">How to sign apps [using the Sign Tool.](https://docs.microsoft.com/windows/win32/appxpkg/how-to-sign-a-package-using-signtool)</span></span>

**<span data-ttu-id="1fedb-133">Zertifikatoptionen:</span><span class="sxs-lookup"><span data-stu-id="1fedb-133">Certificate options:</span></span>**

- [<span data-ttu-id="1fedb-134">Liste der vertrauenswürdigen MS-Zertifizierungsstelle</span><span class="sxs-lookup"><span data-stu-id="1fedb-134">MS Trusted CA List</span></span>](https://ccadb-public.secure.force.com/microsoft/IncludedCACertificateReportForMSFT)

**<span data-ttu-id="1fedb-135">Entscheiden Sie sich für eine Zertifikat Bereitstellungsmethode.</span><span class="sxs-lookup"><span data-stu-id="1fedb-135">Pick a certificate deployment method.</span></span>**

- <span data-ttu-id="1fedb-136">[Bereitstellungspakete](hololens-provisioning.md) können auf lokale Geräte angewendet werden.</span><span class="sxs-lookup"><span data-stu-id="1fedb-136">[Provisioning Packages](hololens-provisioning.md) can be applied to local devices.</span></span>
- <span data-ttu-id="1fedb-137">MDM kann verwendet werden, um [Zertifikate mit Gerätekonfigurationen anzuwenden](https://docs.microsoft.com/mem/intune/protect/certificates-configure).</span><span class="sxs-lookup"><span data-stu-id="1fedb-137">MDM can be used to [apply certificates with device configurations](https://docs.microsoft.com/mem/intune/protect/certificates-configure).</span></span>
- <span data-ttu-id="1fedb-138">Verwenden Sie den [Zertifikat-Manager](certificate-manager.md)für Geräte.</span><span class="sxs-lookup"><span data-stu-id="1fedb-138">Use the on device [Certificate Manager](certificate-manager.md).</span></span>

## <span data-ttu-id="1fedb-139">Installationsmethode</span><span class="sxs-lookup"><span data-stu-id="1fedb-139">Installation method</span></span>

1. <span data-ttu-id="1fedb-140">Überprüfen Sie, ob Ihr Gerät als verwaltet angesehen wird.</span><span class="sxs-lookup"><span data-stu-id="1fedb-140">Check that your device is not considered managed.</span></span>
1. <span data-ttu-id="1fedb-141">Vergewissern Sie sich, dass Ihr HoloLens 2-Gerät eingeschaltet ist und Sie angemeldet sind.</span><span class="sxs-lookup"><span data-stu-id="1fedb-141">Check that your HoloLens 2 device is powered on and you are signed in.</span></span>
1. <span data-ttu-id="1fedb-142">Navigieren Sie auf Ihrem PC zu Ihrer benutzerdefinierten APP, und kopieren Sie yourapp. appxbundle nach yourdevicename\Internal Storage\Downloads.</span><span class="sxs-lookup"><span data-stu-id="1fedb-142">On your PC navigate to your custom app, and copy yourapp.appxbundle to yourdevicename\Internal Storage\Downloads.</span></span>
    <span data-ttu-id="1fedb-143">Nachdem Sie das Kopieren der Datei abgeschlossen haben, können Sie Ihr Gerät trennen und die Installation später abschließen.</span><span class="sxs-lookup"><span data-stu-id="1fedb-143">After you finish copying your file, you may disconnect your device and finish the install later.</span></span>
1. <span data-ttu-id="1fedb-144">Öffnen Sie auf Ihrem HoloLens 2-Gerät das **Startmenü**, wählen Sie **alle apps** aus, und starten Sie die **Datei-Explorer** -app.</span><span class="sxs-lookup"><span data-stu-id="1fedb-144">From your HoloLens 2 device Open the **Start Menu**, select **All apps** and launch the **File Explorer** app.</span></span>
1. <span data-ttu-id="1fedb-145">Navigieren Sie zum Ordner Downloads.</span><span class="sxs-lookup"><span data-stu-id="1fedb-145">Navigate to the Downloads folder.</span></span> <span data-ttu-id="1fedb-146">Möglicherweise müssen Sie auf der linken Seite der APP zuerst **dieses Gerät** auswählen und dann zu Downloads navigieren.</span><span class="sxs-lookup"><span data-stu-id="1fedb-146">You may need to on the left panel of the app select **This device** first, then navigate to Downloads.</span></span>
1. <span data-ttu-id="1fedb-147">Wählen Sie die Datei "yourapp. appxbundle" aus.</span><span class="sxs-lookup"><span data-stu-id="1fedb-147">Select the yourapp.appxbundle file.</span></span>
1. <span data-ttu-id="1fedb-148">Das App-Installationsprogramm wird gestartet.</span><span class="sxs-lookup"><span data-stu-id="1fedb-148">The App Installer will launch.</span></span> <span data-ttu-id="1fedb-149">Wählen Sie die Schaltfläche **Installieren** aus, um Ihre APP zu installieren.</span><span class="sxs-lookup"><span data-stu-id="1fedb-149">Select the **Install** button to install your app.</span></span>

<span data-ttu-id="1fedb-150">Die installierte APP wird nach Abschluss der Installation automatisch gestartet.</span><span class="sxs-lookup"><span data-stu-id="1fedb-150">The installed app will automatically launch upon the completion of installing.</span></span>

![Installieren von MRTK-Beispielen über das App-Installationsprogramm](images/hololens-app-installer-picture.jpg)

### <span data-ttu-id="1fedb-152">Problembehandlung bei Installationen</span><span class="sxs-lookup"><span data-stu-id="1fedb-152">Troubleshooting Installs</span></span>

<span data-ttu-id="1fedb-153">Wenn Ihre APP nicht installiert werden konnte, prüfen Sie die folgenden Schritte zur Problembehandlung:</span><span class="sxs-lookup"><span data-stu-id="1fedb-153">If your app failed to install check the following to troubleshoot:</span></span>

- <span data-ttu-id="1fedb-154">Ihre APP ist entweder ein Master-oder Release-Build.</span><span class="sxs-lookup"><span data-stu-id="1fedb-154">Your app is either a Master or Release build.</span></span>
- <span data-ttu-id="1fedb-155">Ihr Gerät wird auf einen Build aktualisiert, auf dem dieses Feature verfügbar ist.</span><span class="sxs-lookup"><span data-stu-id="1fedb-155">Your device is updated to a build on which this feature is available.</span></span>
- <span data-ttu-id="1fedb-156">Sie sind [mit dem Internet verbunden](hololens-network.md).</span><span class="sxs-lookup"><span data-stu-id="1fedb-156">You are [connected to the internet](hololens-network.md).</span></span>
- <span data-ttu-id="1fedb-157">Ihre [Endpunkte für den Microsoft Store](hololens-offline.md) sind ordnungsgemäß konfiguriert.</span><span class="sxs-lookup"><span data-stu-id="1fedb-157">Your [endpoints for the Microsoft Store](hololens-offline.md) are correctly configured.</span></span>  

## <span data-ttu-id="1fedb-158">Web Installer</span><span class="sxs-lookup"><span data-stu-id="1fedb-158">Web Installer</span></span>

<span data-ttu-id="1fedb-159">Benutzer können eine APP direkt von einem Webserver installieren.</span><span class="sxs-lookup"><span data-stu-id="1fedb-159">Users can install an app directly from a web server.</span></span> <span data-ttu-id="1fedb-160">Dieser Flow nutzt das App-Installationsprogramm kombiniert mit einer einfachen Download-und Installations Verteilungsmethode.</span><span class="sxs-lookup"><span data-stu-id="1fedb-160">This flow takes use of the App Installer combined with an easy download and install distribution method.</span></span>

### <span data-ttu-id="1fedb-161">Einrichten der Web-Installation:</span><span class="sxs-lookup"><span data-stu-id="1fedb-161">How to set up web install:</span></span>

1. <span data-ttu-id="1fedb-162">Stellen Sie sicher, dass Ihre APP für die Installation richtig konfiguriert ist.</span><span class="sxs-lookup"><span data-stu-id="1fedb-162">Ensure your app is correctly configured to install.</span></span>
1. <span data-ttu-id="1fedb-163">Führen Sie die folgenden [Schritte aus, um die Installation von einer Webseite aus zu aktivieren](https://docs.microsoft.com/windows/msix/app-installer/installing-windows10-apps-web#how-to-enable-this-on-a-webpage).</span><span class="sxs-lookup"><span data-stu-id="1fedb-163">Follow these [steps to enable install from a web page](https://docs.microsoft.com/windows/msix/app-installer/installing-windows10-apps-web#how-to-enable-this-on-a-webpage).</span></span>

### <span data-ttu-id="1fedb-164">Benutzerfreundlichkeit:</span><span class="sxs-lookup"><span data-stu-id="1fedb-164">End user experience:</span></span>

1. <span data-ttu-id="1fedb-165">Der Benutzer empfängt und installiert das Zertifikat auf dem Gerät mithilfe einer zuvor ausgewählten Methode.</span><span class="sxs-lookup"><span data-stu-id="1fedb-165">User receives and installs certificate to the device using a method previously chosen above.</span></span>
1. <span data-ttu-id="1fedb-166">Der Benutzer besucht die URL, die aus dem obigen Schritt erstellt wurde.</span><span class="sxs-lookup"><span data-stu-id="1fedb-166">User visits the URL created from the step above.</span></span>

<span data-ttu-id="1fedb-167">Die APP wird nun auf dem Gerät installiert.</span><span class="sxs-lookup"><span data-stu-id="1fedb-167">The app will now install to the device.</span></span> <span data-ttu-id="1fedb-168">Um die APP zu finden, öffnen Sie das **Startmenü** , und wählen Sie die Schaltfläche **alle apps** aus, um Ihre APP zu finden.</span><span class="sxs-lookup"><span data-stu-id="1fedb-168">To find the app, open the **Start menu** and select the **All apps** button to find your app.</span></span>

- <span data-ttu-id="1fedb-169">Weitere Hilfe zur Problembehandlung der Installationsmethode des App-Installationsprogramms finden Sie unter [Behandeln von Problemen](https://docs.microsoft.com/windows/msix/app-installer/troubleshoot-appinstaller-issues)mit dem App-Installationsprogramm.</span><span class="sxs-lookup"><span data-stu-id="1fedb-169">For more help with troubleshooting the app installer installation method visit [troubleshoot app installer issues](https://docs.microsoft.com/windows/msix/app-installer/troubleshoot-appinstaller-issues).</span></span>

> [!NOTE]
> <span data-ttu-id="1fedb-170">Die Benutzeroberfläche wird während des Aktualisierungsvorgangs nicht unterstützt.</span><span class="sxs-lookup"><span data-stu-id="1fedb-170">UI during the update process is not supported.</span></span> <span data-ttu-id="1fedb-171">Daher werden die ShowPrompt-Option auf [dieser Seite](https://docs.microsoft.com/windows/msix/app-installer/update-settings) und die zugehörigen Optionen nicht unterstützt.</span><span class="sxs-lookup"><span data-stu-id="1fedb-171">So the ShowPrompt option on [this page](https://docs.microsoft.com/windows/msix/app-installer/update-settings) and related options are not supported.</span></span>

## <span data-ttu-id="1fedb-172">Beispiel-apps</span><span class="sxs-lookup"><span data-stu-id="1fedb-172">Sample Apps</span></span>

<span data-ttu-id="1fedb-173">Wenn Sie das App-Installationsprogramm mit einigen Beispiel-Apps testen möchten, schauen Sie sich einige der verfügbaren Beispiele an:</span><span class="sxs-lookup"><span data-stu-id="1fedb-173">To try the App Installer with some sample apps check out some of our available samples:</span></span>

- [<span data-ttu-id="1fedb-174">MRTK examples Hub</span><span class="sxs-lookup"><span data-stu-id="1fedb-174">MRTK Examples Hub</span></span>](https://microsoft.github.io/MixedRealityToolkit-Unity/Documentation/README_ExampleHub.html)
- [<span data-ttu-id="1fedb-175">Flächen</span><span class="sxs-lookup"><span data-stu-id="1fedb-175">Surfaces</span></span>](https://docs.microsoft.com/windows/mixed-reality/develop/unity/sampleapp-surfaces)
- [<span data-ttu-id="1fedb-176">UWP-Beispiel-apps, die für Tests verwendet werden können</span><span class="sxs-lookup"><span data-stu-id="1fedb-176">UWP Sample Apps that can be used for testing</span></span>](https://github.com/microsoft/Windows-universal-samples/tree/master/Samples)
