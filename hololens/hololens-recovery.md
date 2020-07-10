---
title: HoloLens neu starten, zurücksetzen oder wiederherstellen
ms.reviewer: Both basic and advanced instructions for rebooting or resetting your HoloLens.
description: Verwenden von Advanced Recovery Companion (ARC), um einen Flashs eines Images in HoloLens 2 auszuführen.
keywords: Hilfe & Anleitung, Neustart, zurücksetzen, wiederherstellen, Kaltstart, Warmstart, Energiezyklus, HoloLens, Herunterfahren, ARC, Advanced Recovery Companion
ms.prod: hololens
ms.sitesec: library
author: mattzmsft
ms.author: mazeller
ms.date: 04/27/2020
ms.custom:
- CI 111456
- CSSTroubleshooting
ms.topic: article
ms.localizationpriority: high
manager: jarrettr
ms.openlocfilehash: 2c7fa9b8c86900c89bbced1a10f3e9e2bc69bcd0
ms.sourcegitcommit: 29755f5af0086a43c532fb5a9a4ae65c36bc82de
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 07/07/2020
ms.locfileid: "10857763"
---
# <span data-ttu-id="9f001-104">HoloLens neu starten, zurücksetzen oder wiederherstellen</span><span class="sxs-lookup"><span data-stu-id="9f001-104">Restart, reset, or recover HoloLens</span></span>

## <span data-ttu-id="9f001-105">Aufladen des Geräts</span><span class="sxs-lookup"><span data-stu-id="9f001-105">Charging the device</span></span>

<span data-ttu-id="9f001-106">Bevor Sie eine Problembehandlung starten, vergewissern Sie sich, dass Ihr Gerät nach Möglichkeit mindestens zu 20% bis 40% aufgeladen ist.</span><span class="sxs-lookup"><span data-stu-id="9f001-106">Before starting any troubleshooting procedure, if possible, ensure that your device is charged at least between 20% and 40%.</span></span>

<span data-ttu-id="9f001-107">Stellen Sie sicher, dass Sie das Ladegerät und das USB-Typ-C-Kabel verwenden, die mit dem HoloLens2-Gerät geliefert wurden.</span><span class="sxs-lookup"><span data-stu-id="9f001-107">Please ensure you are using the charger and the USB Type-C cables that come with the HoloLens2 device.</span></span> <span data-ttu-id="9f001-108">Falls diese nicht verfügbar sind, stellen Sie sicher, dass das verfügbare Ladegerät mindestens 15W Leistung erbringen kann.</span><span class="sxs-lookup"><span data-stu-id="9f001-108">In case they are not available ensure the charger available can support at least 15W of power.</span></span>

> [!NOTE]
> <span data-ttu-id="9f001-109">Verwenden Sie nach Möglichkeit keinen PC, um das Gerät über USB aufzuladen, da dies eine sehr langsame Aufladung zur Folge hat.</span><span class="sxs-lookup"><span data-stu-id="9f001-109">If possible, do not use a PC to charge the device over USB as this will provide a very slow charge.</span></span>

<span data-ttu-id="9f001-110">Wenn das Gerät korrekt hochgefahren ist und ausgeführt wird, gibt es drei verschiedene Möglichkeiten, den Ladezustand des Akkus zu überprüfen.</span><span class="sxs-lookup"><span data-stu-id="9f001-110">If the device is correctly booted and running there are three different ways of checking the charge of your battery.</span></span>

1. <span data-ttu-id="9f001-111">Über das Hauptmenü der Benutzeroberfläche des HoloLens-Geräts.</span><span class="sxs-lookup"><span data-stu-id="9f001-111">From the main menu of the HoloLens Device UI.</span></span>
2. <span data-ttu-id="9f001-112">Verwenden Sie die LED in der Nähe des Einschaltknopfs (bei 40% sollten mindestens zwei LEDs ununterbrochen leuchten).</span><span class="sxs-lookup"><span data-stu-id="9f001-112">Using the LED close to the power button (for 40% you should see at least two solid LEDS).</span></span>
3. <span data-ttu-id="9f001-113">Öffnen Sie auf Ihrem Host-PC das Fenster des Datei-Explorers, und suchen Sie Ihr HoloLens 2-Gerät auf der linken Seite unter "Dieser PC".</span><span class="sxs-lookup"><span data-stu-id="9f001-113">On your Host PC open File Explorer window and look for your HoloLens 2 device on left side under “This PC”.</span></span>
    
      <span data-ttu-id="9f001-114">a.</span><span class="sxs-lookup"><span data-stu-id="9f001-114">a.</span></span> <span data-ttu-id="9f001-115">Klicken Sie mit der rechten Maustaste auf den Namen des Geräts, und wählen Sie "Eigenschaften" aus.</span><span class="sxs-lookup"><span data-stu-id="9f001-115">Right click on the name of the device and select properties.</span></span> <span data-ttu-id="9f001-116">Es wird ein Dialogfeld mit dem Akkustand für Ihr Gerät angezeigt.</span><span class="sxs-lookup"><span data-stu-id="9f001-116">A dialog will appear showing the battery level for your device.</span></span>

![HoloLens 2 ResetRecovery](images/ResetRecovery2.png)

<span data-ttu-id="9f001-118">Wenn das Gerät nicht über das Startmenü gestartet werden kann, beachten Sie bitte die LEDs und die Aufzählung auf dem Host-PC und befolgen Sie die Anleitung zur Fehlerbehebung (https://docs.microsoft.com/hololens/hololens-troubleshooting).</span><span class="sxs-lookup"><span data-stu-id="9f001-118">If the device cannot be booted to the Startup Menu, please take note of the LEDs and enumeration on the host PC and follow the troubleshooting guide (https://docs.microsoft.com/hololens/hololens-troubleshooting).</span></span> <span data-ttu-id="9f001-119">Falls der Status des Geräts nicht in einen der im Handbuch zur Fehlerbehebung aufgeführten Zustände fällt, führen Sie den **Hard-Reset-Vorgang** aus, ohne das Gerät erneut an Ihren Host-PC anzuschließen, sondern schließen Sie es stattdessen an das Netzteil an.</span><span class="sxs-lookup"><span data-stu-id="9f001-119">In case the state of the device does not fall in any of the states listed in the troubleshooting guide, execute the **hard reset procedure** without reconnecting the device to your host PC, but connect it instead to the power supply.</span></span> <span data-ttu-id="9f001-120">Warten Sie mindestens eine Stunde, bis das Gerät aufgeladen ist.</span><span class="sxs-lookup"><span data-stu-id="9f001-120">Wait for at least one hour for the device to charge.</span></span>

## <span data-ttu-id="9f001-121">Setzen Sie das Gerät zurück</span><span class="sxs-lookup"><span data-stu-id="9f001-121">Reset the device</span></span>

<span data-ttu-id="9f001-122">Unter bestimmten Umständen muss der Kunde das Gerät möglicherweise manuell zurücksetzen, ohne die SW-Benutzeroberfläche zu verwenden.</span><span class="sxs-lookup"><span data-stu-id="9f001-122">Under certain circumstances the customer may be required to manually reset the device without using the SW UI.</span></span> 

### <span data-ttu-id="9f001-123">Standardvorgehensweise</span><span class="sxs-lookup"><span data-stu-id="9f001-123">Standard procedure</span></span>
1. <span data-ttu-id="9f001-124">Trennen Sie das Gerät von der Stromversorgung oder dem Host-PC, indem Sie das Typ-C-Kabel ausstecken.</span><span class="sxs-lookup"><span data-stu-id="9f001-124">Disconnect the device from the power supply or the host PC by unplugging the Type-C cable.</span></span>

2. <span data-ttu-id="9f001-125">Halten Sie den **Einschaltknopf** 15 Sekunden lang gedrückt.</span><span class="sxs-lookup"><span data-stu-id="9f001-125">Press and hold the **power button** for 15 seconds.</span></span> <span data-ttu-id="9f001-126">Alle LEDs sollten aus sein.</span><span class="sxs-lookup"><span data-stu-id="9f001-126">All LEDs should be off.</span></span>

3. <span data-ttu-id="9f001-127">Warten Sie 2-3 Sekunden und drücken Sie kurz den **Einschaltknopf**. Die LEDs in der Nähe des Netzschalters leuchten auf und das Gerät startet.</span><span class="sxs-lookup"><span data-stu-id="9f001-127">Wait 2-3 seconds and Short press the **power button**, the LEDs close to the power button will light up and the device will start to boot.</span></span> 

4. <span data-ttu-id="9f001-128">Schließen Sie das Gerät an den Host-PC an, öffnen Sie den Geräte-Manager (drücken Sie für Windows 10 die **„Windows-Taste“** und dann die **„x-Taste“** und klicken Sie auf „Geräte-Manager“) und stellen Sie sicher, dass das Gerät korrekt als Microsoft HoloLens aufgeführt ist siehe Bilder unten:</span><span class="sxs-lookup"><span data-stu-id="9f001-128">Connect the device to the host PC, open Device Manager (for Windows 10 press the **“Windows” key** and then the **“x” key** and click on “Device Manager”) and make sure the device enumerates correctly as Microsoft HoloLens as shown in the pictures below:</span></span>

![HoloLens 2 MicrosoftHoloLensRecovery](images/MicrosoftHoloLens_DeviceManager.png)

### <span data-ttu-id="9f001-130">Hard-Reset-Verfahren</span><span class="sxs-lookup"><span data-stu-id="9f001-130">Hard-reset procedure</span></span>

<span data-ttu-id="9f001-131">Wenn das Standard-Reset-Verfahren nicht funktioniert, können Sie das Hard-Reset-Verfahren verwenden.</span><span class="sxs-lookup"><span data-stu-id="9f001-131">If the standard reset procedure does not work, you can use the hard-reset procedure.</span></span>

1. <span data-ttu-id="9f001-132">Trennen Sie das Gerät von der Stromversorgung oder dem Host-PC, indem Sie das Typ-C-Kabel ausstecken.</span><span class="sxs-lookup"><span data-stu-id="9f001-132">Disconnect the device from the power supply or the host PC by unplugging the Type-C cable.</span></span>

2. <span data-ttu-id="9f001-133">Halten Sie den **Leiser-Knopf + den Einschaltknopf** 15 Sekunden lang gedrückt.</span><span class="sxs-lookup"><span data-stu-id="9f001-133">Hold **volume down + power button** for 15 seconds.</span></span>

3. <span data-ttu-id="9f001-134">Das Gerät wird automatisch neu gestartet.</span><span class="sxs-lookup"><span data-stu-id="9f001-134">The device will automatically reboot.</span></span> 

4. <span data-ttu-id="9f001-135">Schließen Sie das Gerät an den Host-PC an, öffnen Sie den Geräte-Manager (drücken Sie für Windows 10 die **„Windows-Taste“** und dann die **„x-Taste“** und klicken Sie auf „Geräte-Manager“) und stellen Sie sicher, dass das Gerät korrekt als Microsoft HoloLens aufgeführt ist siehe Bilder unten.</span><span class="sxs-lookup"><span data-stu-id="9f001-135">Connect the device to the host PC, open Device Manager (for Windows 10 press the **“Windows” key** and then the **“x” key** and click on “Device Manager”) and make sure the device enumerates correctly as Microsoft HoloLens as shown in the pictures below.</span></span>

![HoloLens 2 MicrosoftHoloLensRecovery](images/MicrosoftHoloLens_DeviceManager.png)

## <span data-ttu-id="9f001-137">Clean-Reflash des Geräts</span><span class="sxs-lookup"><span data-stu-id="9f001-137">Clean reflash the device</span></span>

<span data-ttu-id="9f001-138">In außergewöhnlichen Situationen müssen Sie das Gerät möglicherweise clean flashen.</span><span class="sxs-lookup"><span data-stu-id="9f001-138">In extraordinary situations you may be required to clean flash the device.</span></span> <span data-ttu-id="9f001-139">Es gibt zwei Möglichkeiten, ein HoloLens2-Gerät reflashen.</span><span class="sxs-lookup"><span data-stu-id="9f001-139">There are two ways to reflash a HoloLens2 device.</span></span> <span data-ttu-id="9f001-140">Für alle Reflashing-Verfahren müssen Sie die [Advanced Recovery Companion-Anwendung aus dem Windows Store installieren](https://www.microsoft.com/store/productId/9P74Z35SFRS8).</span><span class="sxs-lookup"><span data-stu-id="9f001-140">For all reflashing procedures you will be required to [install the Advanced Recovery Companion app from the Windows Store](https://www.microsoft.com/store/productId/9P74Z35SFRS8).</span></span> <span data-ttu-id="9f001-141">Wenn Sie Ihr Gerät zurücksetzen, werden alle Ihre persönlichen Daten, Apps und Einstellungen gelöscht, einschließlich der TPM-Zurücksetzung.</span><span class="sxs-lookup"><span data-stu-id="9f001-141">If you reset your device, all your personal data, apps, and settings will be erased, including TPM reset.</span></span>

<span data-ttu-id="9f001-142">Advanced Recovery Companion ist derzeit so eingestellt, dass das Feature Release für [Windows Holographic 2004](hololens-release-notes.md#windows-holographic-version-2004) heruntergeladen wird. Wenn Sie die neueste HoloLens 2 FFU herunterladen möchten, um Ihr Gerät über Advanced Recovery Companion zu flashen, können Sie sie [hier](https://aka.ms/hololens2download) herunterladen.</span><span class="sxs-lookup"><span data-stu-id="9f001-142">Advanced Recovery Companion is currently set to download the feature release build for [Windows Holographic 2004](hololens-release-notes.md#windows-holographic-version-2004), if you would like to download the latest HoloLens 2 FFU to flash your device via Advanced Recovery Companion then you may download it from [here](https://aka.ms/hololens2download).</span></span> <span data-ttu-id="9f001-143">Dies wird auf dem neuesten Stand gehalten und entspricht dem neuesten allgemein verfügbaren Build.</span><span class="sxs-lookup"><span data-stu-id="9f001-143">This is kept up-to-date and will match the latest generally available build.</span></span> 

<span data-ttu-id="9f001-144">Stellen Sie vor dem Starten des Flashens sicher, dass die Anwendung auf Ihrem Windows 10-PC installiert ist und ausgeführt wird und bereit ist, das Gerät zu erkennen.</span><span class="sxs-lookup"><span data-stu-id="9f001-144">Before starting the flashing procedure make sure the app is installed and running on your Windows 10 PC and ready to detect the device.</span></span>

![HoloLens 2 Clean Reflash](images/ARC1.png)

### <span data-ttu-id="9f001-146">Normales Verfahren</span><span class="sxs-lookup"><span data-stu-id="9f001-146">Normal procedure</span></span>

1. <span data-ttu-id="9f001-147">Während das HoloLens-Gerät ausgeführt wird, verbinden Sie es mit Ihrem Windows 10-PC, auf dem Sie zuvor die Advanced Recovery Companion-Anwendung gestartet haben.</span><span class="sxs-lookup"><span data-stu-id="9f001-147">While the HoloLens device is running, connect it to your Windows 10 PC where you previously launched the Advanced Recovery Companion App.</span></span>

2. <span data-ttu-id="9f001-148">Das Gerät wird automatisch erkannt und die Benutzeroberfläche der Advanced Recovery Companion-Anwendung wird wie folgt aktualisiert:</span><span class="sxs-lookup"><span data-stu-id="9f001-148">The device will automatically be detected and the Advanced Recovery Companion App UI will update as follows:</span></span>

![HoloLens 2 Clean Reflash](images/ARC2.png)

3. <span data-ttu-id="9f001-150">Wählen Sie das HoloLens2-Gerät in der Benutzeroberfläche der Advanced Recovery Companion-Anwendung aus und befolgen Sie die Anweisungen, um das Flashen abzuschließen.</span><span class="sxs-lookup"><span data-stu-id="9f001-150">Select the HoloLens2 device in the Advanced Recovery Companion App UI and follow the instructions to complete the flashing.</span></span>

### <span data-ttu-id="9f001-151">Manuelle Vorgehensweise</span><span class="sxs-lookup"><span data-stu-id="9f001-151">Manual procedure</span></span>

<span data-ttu-id="9f001-152">Wenn das Gerät nicht richtig startet, müssen Sie das HoloLens 2-Gerät möglicherweise in den Wiederherstellungsmodus versetzen.</span><span class="sxs-lookup"><span data-stu-id="9f001-152">If the device does not boot correctly you may need to put the HoloLens 2 device in Recovery mode.</span></span>

1. <span data-ttu-id="9f001-153">Trennen Sie das Gerät von der Stromversorgung oder dem Host-PC, indem Sie das Typ-C-Kabel ausstecken.</span><span class="sxs-lookup"><span data-stu-id="9f001-153">Disconnect the device from the power supply or the host PC by unplugging the Type-C cable.</span></span> 

2. <span data-ttu-id="9f001-154">Halten Sie den **Einschaltknopf** 15 Sekunden lang gedrückt.</span><span class="sxs-lookup"><span data-stu-id="9f001-154">Press and hold the **power button** for 15 seconds.</span></span> <span data-ttu-id="9f001-155">Alle LEDs sollten erlöschen.</span><span class="sxs-lookup"><span data-stu-id="9f001-155">All LEDs should turn off.</span></span> 

3. <span data-ttu-id="9f001-156">Halten Sie den **Einschaltknopf** gedrückt, während Sie die **Lauter-Taste** drücken, um das Gerät zu starten.</span><span class="sxs-lookup"><span data-stu-id="9f001-156">While pressing the **volume up button**, press and release the **power button** to boot the device.</span></span> <span data-ttu-id="9f001-157">Warten Sie 15 Sekunden, bevor Sie die Lauter-Taste loslassen.</span><span class="sxs-lookup"><span data-stu-id="9f001-157">Wait 15 seconds before releasing the volume up button.</span></span> <span data-ttu-id="9f001-158">Von den 5 LEDs am Gerät leuchtet nur die mittlere LED auf.</span><span class="sxs-lookup"><span data-stu-id="9f001-158">Out of the 5 LEDs on the device, only the middle LED will light up.</span></span>

4. <span data-ttu-id="9f001-159">Schließen Sie das Gerät an den Host-PC an, öffnen Sie den Geräte-Manager (drücken Sie für Windows 10 die **„Windows-Taste“** und dann die **„x-Taste“** und klicken Sie auf „Geräte-Manager“) und stellen Sie sicher, dass das Gerät korrekt als Microsoft HoloLens aufgeführt ist siehe Bild unten.</span><span class="sxs-lookup"><span data-stu-id="9f001-159">Connect the device to the host PC, open Device Manager (for Windows 10 press the **“Windows” key** and then the **“x” key** and click on “Device Manager”) and make sure the device enumerates correctly as Microsoft HoloLens as shown in the image below.</span></span>

![HoloLens 2 MicrosoftHoloLensRecovery](images/MicrosoftHoloLensRecovery.png)

5. <span data-ttu-id="9f001-161">Das Gerät wird automatisch erkannt und die Benutzeroberfläche der Advanced Recovery Companion-Anwendung wird wie folgt aktualisiert:</span><span class="sxs-lookup"><span data-stu-id="9f001-161">The device will be automatically detected, and the Advanced Recovery Companion app UI will update as follows:</span></span>

![HoloLens 2 Clean Reflash](images/ARC2.png)

6. <span data-ttu-id="9f001-163">Wählen Sie das HoloLens 2-Gerät in der Benutzeroberfläche der Advanced Recovery Companion-Anwendung aus und befolgen Sie die Anweisungen, um das Flashen abzuschließen.</span><span class="sxs-lookup"><span data-stu-id="9f001-163">Select the HoloLens 2 device in the Advanced Recovery Companion app UI and follow the instructions to complete the flashing.</span></span>

## <span data-ttu-id="9f001-164">Herunterladen von ARC ohne Verwendung des App Store</span><span class="sxs-lookup"><span data-stu-id="9f001-164">Downloading ARC without using the app store</span></span>

<span data-ttu-id="9f001-165">Wenn eine IT-Umgebung die Verwendung der Windows Store-App verhindert oder den Zugriff auf das Einzelhandelsgeschäft einschränkt, können IT-Administratoren diese Anwendung über andere "Offline"-Bereitstellungspfade verfügbar machen.</span><span class="sxs-lookup"><span data-stu-id="9f001-165">If an IT environment prevents the use of the Windows Store app or limits access to the retail store, IT administrators can make this app available through other ‘offline’ deployment paths.</span></span> 

- <span data-ttu-id="9f001-166">Dieser Vorgang kann auch für andere Anwendungen verwendet werden (siehe Schritt 2).</span><span class="sxs-lookup"><span data-stu-id="9f001-166">This process may also be used for other apps, as seen in step 2.</span></span> <span data-ttu-id="9f001-167">Dieses Handbuch konzentriert sich auf Advanced Recovery Companion, kann jedoch für andere Offline-Anwendung geändert werden.</span><span class="sxs-lookup"><span data-stu-id="9f001-167">This guide will focus on Advanced Recovery Companion, but my be modified for other offline apps.</span></span>  

<span data-ttu-id="9f001-168">Dieser Bereitstellungspfad kann mit den folgenden Schritten aktiviert werden:</span><span class="sxs-lookup"><span data-stu-id="9f001-168">This deployment path can be enabled with the following steps:</span></span>
1.  <span data-ttu-id="9f001-169">Rufen Sie die [Store For Business-Website](https://businessstore.microsoft.com) auf und melden Sie sich mit einer Azure AD-Identität an.</span><span class="sxs-lookup"><span data-stu-id="9f001-169">Go to the [Store For Business website](https://businessstore.microsoft.com) and sign-in with an Azure AD identity.</span></span>
1.  <span data-ttu-id="9f001-170">Gehen Sie zu **Verwalten – Einstellungen** und aktivieren Sie **Offline-Anwendungen anzeigen** unter **Einkaufserfahrung**, wie unter https://businessstore.microsoft.com/manage/settings/shop beschrieben</span><span class="sxs-lookup"><span data-stu-id="9f001-170">Go to **Manage – Settings**, and turn on **Show offline apps** under **Shopping experience** as described at https://businessstore.microsoft.com/manage/settings/shop</span></span> 
1.  <span data-ttu-id="9f001-171">Gehen Sie zu **Einkaufen für meine Gruppe** und suchen Sie nach der [Advanced Recovery Companion-Anwendung](https://businessstore.microsoft.com/store/details/advanced-recovery-companion/9P74Z35SFRS8).</span><span class="sxs-lookup"><span data-stu-id="9f001-171">Go to **shop for my group** and search for the [Advanced Recovery Companion](https://businessstore.microsoft.com/store/details/advanced-recovery-companion/9P74Z35SFRS8) app.</span></span>
1.  <span data-ttu-id="9f001-172">Ändern Sie das **Feld Lizenztyp** in Offline und klicken Sie auf **Verwalten**.</span><span class="sxs-lookup"><span data-stu-id="9f001-172">Change the **License Type** box to offline and click **Manage**.</span></span>
1.  <span data-ttu-id="9f001-173">Klicken Sie unter Paket für Offline-Verwendung herunterladen auf die zweite blaue Schaltfläche **"Herunterladen"**.</span><span class="sxs-lookup"><span data-stu-id="9f001-173">Under Download the package for offline use click the second blue **“Download”** button .</span></span> <span data-ttu-id="9f001-174">Stellen Sie sicher, dass die Dateierweiterung .appxbundle ist.</span><span class="sxs-lookup"><span data-stu-id="9f001-174">Ensure the file extension is .appxbundle.</span></span>
1.  <span data-ttu-id="9f001-175">Wenn der Desktop-PC zu diesem Zeitpunkt über einen Internetzugang verfügt, doppelklicken Sie einfach und installieren Sie ihn.</span><span class="sxs-lookup"><span data-stu-id="9f001-175">At this stage, if the Desktop PC has Internet access, simply double click and install.</span></span> 
1.  <span data-ttu-id="9f001-176">Der IT-Administrator kann diese Anwendung auch über System Center Configuration Manager (SCCM) oder Intune verteilen.</span><span class="sxs-lookup"><span data-stu-id="9f001-176">The IT administrator can also distribute this app through System Center Configuration Manager (SCCM) or Intune.</span></span>
1.  <span data-ttu-id="9f001-177">Wenn der Ziel-PC keine Internetverbindung hat, sind einige zusätzliche Schritte erforderlich:</span><span class="sxs-lookup"><span data-stu-id="9f001-177">If the target PC has no Internet connectivity, some additional steps are needed:</span></span> 
    1.  <span data-ttu-id="9f001-178">Wählen Sie die nicht codierte Lizenz aus und klicken Sie auf **"Lizenz generieren"**. Klicken Sie unter **"Erforderliche Frameworks"** auf **"Herunterladen"**.</span><span class="sxs-lookup"><span data-stu-id="9f001-178">Select the unencoded license and click **“Generate license”** and under **“Required Frameworks”** click **“Download.”**</span></span> 
    1.  <span data-ttu-id="9f001-179">PCs ohne Internetzugang müssen DISM verwenden, um das Paket mit der Abhängigkeit und Lizenz anzuwenden.</span><span class="sxs-lookup"><span data-stu-id="9f001-179">PCs without internet access will need to use DISM to apply the package with the dependency and license.</span></span> <span data-ttu-id="9f001-180">Geben Sie an einer Administrator-Eingabeaufforderung Folgendes ein:</span><span class="sxs-lookup"><span data-stu-id="9f001-180">In an administrator command prompt, type:</span></span>

      ```console
      C:\WINDOWS\system32>dism /online /Add-ProvisionedAppxPackage /PackagePath:"C:\ARCoffline\Microsoft.AdvancedRecoveryCompanion_1.19050.1301.0_neutral_~_8wekyb3d8bbwe.appxbundle" /DependencyPackagePath:"C:\ARCoffline\Microsoft.VCLibs.140.00.UWPDesktop_14.0.27629.0_x86__8wekyb3d8bbwe.appx" /LicensePath:"C:\ARCoffline\Microsoft.AdvancedRecoveryCompanion_8wekyb3d8bbwe_f72ce112-dd2e-d771-8827-9cbcbf89f8b5.xml" /Region:all
      ```
> [!NOTE]
> <span data-ttu-id="9f001-181">Die Versionsnummer in diesem Codebeispiel stimmt möglicherweise nicht mit der aktuell verfügbaren Version überein.</span><span class="sxs-lookup"><span data-stu-id="9f001-181">The version number in this code example may not match the currently avalible version.</span></span> <span data-ttu-id="9f001-182">Möglicherweise haben Sie auch einen anderen Download-Speicherort als im angegebenen Beispiel ausgewählt.</span><span class="sxs-lookup"><span data-stu-id="9f001-182">You may have also choosen a different download location than in the example given.</span></span> <span data-ttu-id="9f001-183">Bitte stellen Sie sicher, dass Sie die erforderlichen Änderungen vornehmen.</span><span class="sxs-lookup"><span data-stu-id="9f001-183">Please make sure to make any changes as needed.</span></span>

> [!TIP]
> <span data-ttu-id="9f001-184">Wenn Sie Advanced Recovery Companion verwenden möchten, um eine ffu offline zu installieren, kann es hilfreich sein, Ihr Flash-Image herunterzuladen, um verfügbar zu sein. Hier ist das [aktuelle Image für HoloLens 2](https://aka.ms/hololens2download).</span><span class="sxs-lookup"><span data-stu-id="9f001-184">When planning to use Advanced Recovery Companion to install an ffu offline it may be useful to download your flashing image to be availible, here is the [current image for HoloLens 2](https://aka.ms/hololens2download).</span></span> 

<span data-ttu-id="9f001-185">Andere Ressourcen</span><span class="sxs-lookup"><span data-stu-id="9f001-185">Other resources:</span></span>
- https://docs.microsoft.com/microsoft-store/distribute-offline-apps 
- https://docs.microsoft.com/windows-hardware/manufacture/desktop/dism-app-package--appx-or-appxbundle--servicing-command-line-options


