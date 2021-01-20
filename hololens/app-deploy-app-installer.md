---
title: So laden und installieren Sie Apps über das HoloLens 2-App-Installationsprogramm
description: Laden von Folien und Installieren von Apps über die Benutzeroberfläche
keywords: App-Verwaltung, App, HoloLens, App-Installer
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
ms.openlocfilehash: ab0c58d5a97d5dbaf83adf321d1f9fbc01b3ad03
ms.sourcegitcommit: 37910c10f0f98aa9cbdc29124cd8f14ee0af3fbd
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 01/19/2021
ms.locfileid: "11280654"
---
# <span data-ttu-id="45541-104">Installieren von Apps auf HoloLens 2 über das App-Installationsprogramm</span><span class="sxs-lookup"><span data-stu-id="45541-104">Install Apps on HoloLens 2 via App Installer</span></span>

> [!NOTE]
> <span data-ttu-id="45541-105">Dieses Feature wurde in [Windows Holographic, Version 20H2 – Dezember 2020 Update, verfügbar gemacht.](hololens-release-notes.md)</span><span class="sxs-lookup"><span data-stu-id="45541-105">This feature was made available in [Windows Holographic, version 20H2 – December 2020 Update](hololens-release-notes.md).</span></span> <span data-ttu-id="45541-106">Stellen Sie sicher, dass Ihr [Gerät für](hololens-update-hololens.md) die Verwendung dieses Features aktualisiert ist.</span><span class="sxs-lookup"><span data-stu-id="45541-106">Ensure your device is [updated](hololens-update-hololens.md) to use this feature.</span></span>

<span data-ttu-id="45541-107">Wir haben **eine neue Funktion (App-Installer)** hinzugefügt, mit der Sie Anwendungen nahtloser auf Ihren HoloLens 2-Geräten installieren können.</span><span class="sxs-lookup"><span data-stu-id="45541-107">We have **added a new capability (App Installer) to allow you to install applications more seamlessly** on your HoloLens 2 devices.</span></span> <span data-ttu-id="45541-108">Das Feature ist **für nicht verwaltete Geräte standardmäßig aktiviert.**</span><span class="sxs-lookup"><span data-stu-id="45541-108">The feature will be **on by default for unmanaged devices**.</span></span> <span data-ttu-id="45541-109">Um Unterbrechungen für Unternehmen zu verhindern, steht das App-Installationsprogramm derzeit nicht für **verwaltete** Geräte zur Verfügung.</span><span class="sxs-lookup"><span data-stu-id="45541-109">To prevent disruption to enterprises, app installer will be **not be available for managed devices** at this time.</span></span>  

<span data-ttu-id="45541-110">Ein Gerät wird als "verwaltet" betrachtet, **wenn** eine der folgenden Bedingungen zutrifft:</span><span class="sxs-lookup"><span data-stu-id="45541-110">A device is considered “managed” if **any** of the following are true:</span></span>

- <span data-ttu-id="45541-111">MDM [Enrolled](hololens-enroll-mdm.md)</span><span class="sxs-lookup"><span data-stu-id="45541-111">MDM [Enrolled](hololens-enroll-mdm.md)</span></span>
- <span data-ttu-id="45541-112">Mit [Bereitstellungspaket konfiguriert](hololens-provisioning.md)</span><span class="sxs-lookup"><span data-stu-id="45541-112">Configured with [provisioning package](hololens-provisioning.md)</span></span>
- <span data-ttu-id="45541-113">[Benutzeridentität](hololens-identity.md) ist Azure AD</span><span class="sxs-lookup"><span data-stu-id="45541-113">User [Identity](hololens-identity.md) is Azure AD</span></span>

<span data-ttu-id="45541-114">Sie können jetzt Apps installieren, ohne den Entwicklermodus aktivieren oder das Geräteportal verwenden zu müssen.</span><span class="sxs-lookup"><span data-stu-id="45541-114">You are now able to install Apps without needing to enable Developer Mode or using Device Portal.</span></span>  <span data-ttu-id="45541-115">Laden Sie (über USB oder Microsoft Edge) das Appx Bundle auf Ihr Gerät herunter, und navigieren Sie zum Appx Bundle im Datei-Explorer, um aufgefordert zu werden, die Installation zu starten.</span><span class="sxs-lookup"><span data-stu-id="45541-115">Download (over USB or through Microsoft Edge) the Appx Bundle to your device and navigate to the Appx Bundle in the File Explorer to be prompted to kick off the installation.</span></span>  <span data-ttu-id="45541-116">Alternativ können [Sie eine Installation über eine Webseite initiieren.](https://docs.microsoft.com/windows/msix/app-installer/installing-windows10-apps-web)</span><span class="sxs-lookup"><span data-stu-id="45541-116">Alternatively, [initiate an install from a web page](https://docs.microsoft.com/windows/msix/app-installer/installing-windows10-apps-web).</span></span>  <span data-ttu-id="45541-117">Genau wie Apps, die Sie aus dem Microsoft Store installieren oder mithilfe der BRANCHEN-App-Bereitstellungsfunktion [](https://docs.microsoft.com/windows/win32/appxpkg/how-to-sign-a-package-using-signtool#security-considerations) von MDM querladen, müssen Apps digital mit dem Signierungstool signiert werden, und das zum Signieren verwendete Zertifikat muss vom HoloLens-Gerät als vertrauenswürdig eingestuft werden, bevor die App bereitgestellt werden kann. [](https://docs.microsoft.com/windows/win32/appxpkg/how-to-sign-a-package-using-signtool)</span><span class="sxs-lookup"><span data-stu-id="45541-117">Just like apps you install from the Microsoft Store or sideload using MDM’s LOB App deployment capability, apps need to be digitally signed with the [Sign Tool](https://docs.microsoft.com/windows/win32/appxpkg/how-to-sign-a-package-using-signtool) and the [certificate used to sign must be trusted](https://docs.microsoft.com/windows/win32/appxpkg/how-to-sign-a-package-using-signtool#security-considerations) by the HoloLens device before the app can be deployed.</span></span>

## <span data-ttu-id="45541-118">Anforderungen</span><span class="sxs-lookup"><span data-stu-id="45541-118">Requirements</span></span>

### <span data-ttu-id="45541-119">Für Ihre Geräte:</span><span class="sxs-lookup"><span data-stu-id="45541-119">For your devices:</span></span>

 <span data-ttu-id="45541-120">Das Feature ist derzeit in Windows Holographic 20H2-Builds für HoloLens 2-Geräte verfügbar.</span><span class="sxs-lookup"><span data-stu-id="45541-120">feature is currently available in Windows Holographic 20H2 builds for HoloLens 2 devices.</span></span> <span data-ttu-id="45541-121">Stellen Sie sicher, dass alle Geräte, die diese Methode verwenden, [aktualisiert werden.](hololens-update-hololens.md)</span><span class="sxs-lookup"><span data-stu-id="45541-121">Ensure any devices using this method are [updated](hololens-update-hololens.md).</span></span>

### <span data-ttu-id="45541-122">Für Ihre Apps:</span><span class="sxs-lookup"><span data-stu-id="45541-122">For your apps:</span></span> 
<span data-ttu-id="45541-123">Die Lösungskonfiguration Ihrer App muss entweder **Master** oder **Release** sein, da der App Installer Abhängigkeiten aus dem Store verwendet.</span><span class="sxs-lookup"><span data-stu-id="45541-123">Your app’s Solution Configuration must be either **Master** or **Release** as the App Installer will use dependencies from the store.</span></span> <span data-ttu-id="45541-124">Weitere Informationen zum Erstellen [von App-Paketen.](https://docs.microsoft.com/windows/msix/app-installer/create-appinstallerfile-vs)</span><span class="sxs-lookup"><span data-stu-id="45541-124">See more about [creating app packages](https://docs.microsoft.com/windows/msix/app-installer/create-appinstallerfile-vs).</span></span>

<span data-ttu-id="45541-125">Apps, die über diese Methode installiert werden, müssen digital signiert sein.</span><span class="sxs-lookup"><span data-stu-id="45541-125">Apps that are installed via this method must be digitally signed.</span></span> <span data-ttu-id="45541-126">Sie müssen ein Zertifikat zum Signieren der App verwenden.</span><span class="sxs-lookup"><span data-stu-id="45541-126">You'll need to use a certificate to sign the app.</span></span> <span data-ttu-id="45541-127">Sie können entweder ein Zertifikat aus der [Liste](https://ccadb-public.secure.force.com/microsoft/IncludedCACertificateReportForMSFT)der vertrauenswürdigen MS-Zertifizierungsstellen erhalten. In diesem Fall müssen Sie keine zusätzlichen Maßnahmen ergreifen.</span><span class="sxs-lookup"><span data-stu-id="45541-127">You can either get a certificate from the [MS Trusted CA List](https://ccadb-public.secure.force.com/microsoft/IncludedCACertificateReportForMSFT), in which case you won't need to take any extra action.</span></span> <span data-ttu-id="45541-128">Oder Sie können Ihr eigenes Zertifikat signieren, das Zertifikat muss jedoch auf das Gerät übertragen werden.</span><span class="sxs-lookup"><span data-stu-id="45541-128">Or you can sign your own certificate however that certificate will need to be pushed onto the device.</span></span>

- <span data-ttu-id="45541-129">So signieren Sie Apps [mit dem Signieren-Tool.](https://docs.microsoft.com/windows/win32/appxpkg/how-to-sign-a-package-using-signtool)</span><span class="sxs-lookup"><span data-stu-id="45541-129">How to sign apps [using the Sign Tool.](https://docs.microsoft.com/windows/win32/appxpkg/how-to-sign-a-package-using-signtool)</span></span>

**<span data-ttu-id="45541-130">Zertifikatoptionen:</span><span class="sxs-lookup"><span data-stu-id="45541-130">Certificate options:</span></span>**

- [<span data-ttu-id="45541-131">MS Trusted CA List</span><span class="sxs-lookup"><span data-stu-id="45541-131">MS Trusted CA List</span></span>](https://ccadb-public.secure.force.com/microsoft/IncludedCACertificateReportForMSFT)

**<span data-ttu-id="45541-132">Wählen Sie eine Zertifikatbereitstellungsmethode aus.</span><span class="sxs-lookup"><span data-stu-id="45541-132">Pick a certificate deployment method.</span></span>**

- <span data-ttu-id="45541-133">[Bereitstellungspakete können](hololens-provisioning.md) auf lokale Geräte angewendet werden.</span><span class="sxs-lookup"><span data-stu-id="45541-133">[Provisioning Packages](hololens-provisioning.md) can be applied to local devices.</span></span>
- <span data-ttu-id="45541-134">MDM kann verwendet werden, [um Zertifikate mit Gerätekonfigurationen anzuwenden.](https://docs.microsoft.com/mem/intune/protect/certificates-configure)</span><span class="sxs-lookup"><span data-stu-id="45541-134">MDM can be used to [apply certificates with device configurations](https://docs.microsoft.com/mem/intune/protect/certificates-configure).</span></span>
- <span data-ttu-id="45541-135">Verwenden Sie den [Zertifikat-Manager auf dem Gerät.](certificate-manager.md)</span><span class="sxs-lookup"><span data-stu-id="45541-135">Use the on device [Certificate Manager](certificate-manager.md).</span></span>

## <span data-ttu-id="45541-136">Installationsmethode</span><span class="sxs-lookup"><span data-stu-id="45541-136">Installation method</span></span>

1. <span data-ttu-id="45541-137">Stellen Sie sicher, dass Ihr Gerät nicht als verwaltet betrachtet wird.</span><span class="sxs-lookup"><span data-stu-id="45541-137">Check that your device is not considered managed.</span></span>
1. <span data-ttu-id="45541-138">Überprüfen Sie, ob Ihr HoloLens 2-Gerät eingeschaltet ist und Sie angemeldet sind.</span><span class="sxs-lookup"><span data-stu-id="45541-138">Check that your HoloLens 2 device is powered on and you are signed in.</span></span>
1. <span data-ttu-id="45541-139">Navigieren Sie auf Ihrem PC zu Ihrer benutzerdefinierten App, und kopieren Sie "yourapp.appxbundle" in "yourdevicename\Internal Storage\Downloads".</span><span class="sxs-lookup"><span data-stu-id="45541-139">On your PC navigate to your custom app, and copy yourapp.appxbundle to yourdevicename\Internal Storage\Downloads.</span></span>
    <span data-ttu-id="45541-140">Nachdem Sie das Kopieren der Datei abgeschlossen haben, können Sie das Gerät trennen und die Installation später beenden.</span><span class="sxs-lookup"><span data-stu-id="45541-140">After you finish copying your file, you may disconnect your device and finish the install later.</span></span>
1. <span data-ttu-id="45541-141">Öffnen Sie auf Ihrem HoloLens 2-Gerät das **Startmenü,** wählen Sie **alle Apps aus,** und starten Sie die **Datei-Explorer-App.**</span><span class="sxs-lookup"><span data-stu-id="45541-141">From your HoloLens 2 device Open the **Start Menu**, select **All apps** and launch the **File Explorer** app.</span></span>
1. <span data-ttu-id="45541-142">Navigieren Sie zum Ordner "Downloads".</span><span class="sxs-lookup"><span data-stu-id="45541-142">Navigate to the Downloads folder.</span></span> <span data-ttu-id="45541-143">You may need to on the left panel of the app select **This device** first, then navigate to Downloads.</span><span class="sxs-lookup"><span data-stu-id="45541-143">You may need to on the left panel of the app select **This device** first, then navigate to Downloads.</span></span>
1. <span data-ttu-id="45541-144">Wählen Sie die Datei "yourapp.appxbundle" aus.</span><span class="sxs-lookup"><span data-stu-id="45541-144">Select the yourapp.appxbundle file.</span></span>
1. <span data-ttu-id="45541-145">Das App-Installationsprogramm wird gestartet.</span><span class="sxs-lookup"><span data-stu-id="45541-145">The App Installer will launch.</span></span> <span data-ttu-id="45541-146">Wählen Sie die **Schaltfläche "Installieren"** aus, um Ihre App zu installieren.</span><span class="sxs-lookup"><span data-stu-id="45541-146">Select the **Install** button to install your app.</span></span>

<span data-ttu-id="45541-147">Die installierte App wird nach Abschluss der Installation automatisch gestartet.</span><span class="sxs-lookup"><span data-stu-id="45541-147">The installed app will automatically launch upon the completion of installing.</span></span>

![Installieren von MRTK-Beispielen über den App-Installer](images/hololens-app-installer-picture.jpg)

### <span data-ttu-id="45541-149">Problembehandlung bei Installationen</span><span class="sxs-lookup"><span data-stu-id="45541-149">Troubleshooting Installs</span></span>

<span data-ttu-id="45541-150">Wenn ihre App nicht installiert werden konnte, überprüfen Sie folgendes, um eine Problembehandlung zu beheben:</span><span class="sxs-lookup"><span data-stu-id="45541-150">If your app failed to install,  check the following to troubleshoot:</span></span>

- <span data-ttu-id="45541-151">Ihre App ist entweder ein Master- oder Release-Build.</span><span class="sxs-lookup"><span data-stu-id="45541-151">Your app is either a Master or Release build.</span></span>
- <span data-ttu-id="45541-152">Ihr Gerät wird auf einen Build aktualisiert, auf dem dieses Feature verfügbar ist.</span><span class="sxs-lookup"><span data-stu-id="45541-152">Your device is updated to a build on which this feature is available.</span></span>
- <span data-ttu-id="45541-153">Sie sind [mit dem Internet verbunden.](hololens-network.md)</span><span class="sxs-lookup"><span data-stu-id="45541-153">You are [connected to the internet](hololens-network.md).</span></span>
- <span data-ttu-id="45541-154">Ihre [Endpunkte für den Microsoft Store](hololens-offline.md) sind ordnungsgemäß konfiguriert.</span><span class="sxs-lookup"><span data-stu-id="45541-154">Your [endpoints for the Microsoft Store](hololens-offline.md) are correctly configured.</span></span>  

## <span data-ttu-id="45541-155">Web Installer</span><span class="sxs-lookup"><span data-stu-id="45541-155">Web Installer</span></span>

<span data-ttu-id="45541-156">Benutzer können eine App direkt von einem Webserver installieren.</span><span class="sxs-lookup"><span data-stu-id="45541-156">Users can install an app directly from a web server.</span></span> <span data-ttu-id="45541-157">Dieser Fluss verwendet das App-Installationsprogramm in Kombination mit einer einfachen Download- und Installationsmethode.</span><span class="sxs-lookup"><span data-stu-id="45541-157">This flow takes use of the App Installer combined with an easy download and install distribution method.</span></span>

### <span data-ttu-id="45541-158">So richten Sie die Webinstallation ein:</span><span class="sxs-lookup"><span data-stu-id="45541-158">How to set up web install:</span></span>

1. <span data-ttu-id="45541-159">Stellen Sie sicher, dass Ihre App ordnungsgemäß für die Installation konfiguriert ist.</span><span class="sxs-lookup"><span data-stu-id="45541-159">Ensure your app is correctly configured to install.</span></span>
1. <span data-ttu-id="45541-160">Führen Sie die [folgenden Schritte aus, um die Installation über eine Webseite zu aktivieren.](https://docs.microsoft.com/windows/msix/app-installer/installing-windows10-apps-web#how-to-enable-this-on-a-webpage)</span><span class="sxs-lookup"><span data-stu-id="45541-160">Follow these [steps to enable install from a web page](https://docs.microsoft.com/windows/msix/app-installer/installing-windows10-apps-web#how-to-enable-this-on-a-webpage).</span></span>

### <span data-ttu-id="45541-161">Endbenutzererfahrung:</span><span class="sxs-lookup"><span data-stu-id="45541-161">End user experience:</span></span>

1. <span data-ttu-id="45541-162">Der Benutzer empfängt und installiert das Zertifikat auf dem Gerät mithilfe einer zuvor gewählten Methode.</span><span class="sxs-lookup"><span data-stu-id="45541-162">User receives and installs certificate to the device using a method previously chosen above.</span></span>
1. <span data-ttu-id="45541-163">Der Benutzer besucht die URL, die aus dem obigen Schritt erstellt wurde.</span><span class="sxs-lookup"><span data-stu-id="45541-163">User visits the URL created from the step above.</span></span>

<span data-ttu-id="45541-164">Die App wird nun auf dem Gerät installiert.</span><span class="sxs-lookup"><span data-stu-id="45541-164">The app will now install to the device.</span></span> <span data-ttu-id="45541-165">Um die App zu finden, öffnen Sie das **Startmenü,** und wählen Sie die Schaltfläche **"Alle Apps"** aus, um Ihre App zu finden.</span><span class="sxs-lookup"><span data-stu-id="45541-165">To find the app, open the **Start menu** and select the **All apps** button to find your app.</span></span>

- <span data-ttu-id="45541-166">Weitere Hilfe zur Problembehandlung bei der Installationsmethode des App-Installers finden Sie unter [Behandeln von Problemen mit dem App-Installer.](https://docs.microsoft.com/windows/msix/app-installer/troubleshoot-appinstaller-issues)</span><span class="sxs-lookup"><span data-stu-id="45541-166">For more help with troubleshooting the app installer installation method visit [troubleshoot app installer issues](https://docs.microsoft.com/windows/msix/app-installer/troubleshoot-appinstaller-issues).</span></span>

> [!NOTE]
> <span data-ttu-id="45541-167">Die Benutzeroberfläche während des Updateprozesses wird nicht unterstützt.</span><span class="sxs-lookup"><span data-stu-id="45541-167">UI during the update process is not supported.</span></span> <span data-ttu-id="45541-168">Daher werden die Option "ShowPrompt" auf [dieser Seite und](https://docs.microsoft.com/windows/msix/app-installer/update-settings) verwandte Optionen nicht unterstützt.</span><span class="sxs-lookup"><span data-stu-id="45541-168">So the ShowPrompt option on [this page](https://docs.microsoft.com/windows/msix/app-installer/update-settings) and related options are not supported.</span></span>

## <span data-ttu-id="45541-169">Beispiel-Apps</span><span class="sxs-lookup"><span data-stu-id="45541-169">Sample Apps</span></span>

<span data-ttu-id="45541-170">Wenn Sie den App Installer mit einigen Beispiel-Apps testen möchten, sehen Sie sich einige unserer verfügbaren Beispiele an:</span><span class="sxs-lookup"><span data-stu-id="45541-170">To try the App Installer with some sample apps check out some of our available samples:</span></span>

- [<span data-ttu-id="45541-171">HUB für MRTK-Beispiele</span><span class="sxs-lookup"><span data-stu-id="45541-171">MRTK Examples Hub</span></span>](https://microsoft.github.io/MixedRealityToolkit-Unity/Documentation/README_ExampleHub.html)
- [<span data-ttu-id="45541-172">Oberflächen</span><span class="sxs-lookup"><span data-stu-id="45541-172">Surfaces</span></span>](https://docs.microsoft.com/windows/mixed-reality/develop/unity/sampleapp-surfaces)
- [<span data-ttu-id="45541-173">UWP-Beispiel-Apps, die zum Testen verwendet werden können</span><span class="sxs-lookup"><span data-stu-id="45541-173">UWP Sample Apps that can be used for testing</span></span>](https://github.com/microsoft/Windows-universal-samples/tree/master/Samples)
